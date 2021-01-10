# HandlerMethodArgumentResolver란?

컨트롤러 메소드에서 반복적으로 세션값을 가져올 때 사용하는데,
특정 조건에 맞는 파라미터가 있을 때 원하는 값을 어노테이션을 통해 바로 가져올 수 있습니다.

# 사용 예제
컨트롤러에 SessionUser라는 객체가 필요할 때 가져오는 예시를 보겠습니다. </br>
*이동욱 님의 '스프링 부트와 AWS로 혼자 구현하는 웹서비스'에 나오는 내용입니다.</br>
*[참조: KingCjy님의 velog](https://velog.io/@kingcjy/Spring-HandlerMethodArgumentResolver%EC%9D%98-%EC%82%AC%EC%9A%A9%EB%B2%95%EA%B3%BC-%EB%8F%99%EC%9E%91%EC%9B%90%EB%A6%AC)

**1. 어노테이션 작성**
```
import java.lang.annotation.ElementType;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.annotation.Target;

@Target(ElementType.PARAMETER) // 이 어노테이션이 생성될 수 있는 위치 지정, PARAMETER이므로 메소드의 파라미터로 선언된 객체에서만 사용
@Retention(RetentionPolicy.RUNTIME)
public @interface LoginUser {
}
```

**2. 객체와 컨트롤러 작성인데, 여기서는 미리 만들어진 SessionUser 객체와 IndexController를 사용합니다.**
컨트롤러 코드
```
public class IndexController {

    private final PostsService postsService;
    private final HttpSession httpSession;

    @GetMapping("/")
    public String index(Model model, @LoginUser SessionUser user)
```

**3. resolver 작성**
HandlerMethodArgumentResolver를 상속받은 원하는 클래스를 만들어줍니다. 여기서는 LoginUserArgumentResolver를 사용합니다.
이 클래스는 `boolean supportsParameter`, `Object resolveArgument` 메소드를 구현해야 합니다.
- `supportsParameter` 는 현재 파라미터를 resolver가 지원하는지에 대한 boolean을 리턴합니다.
- `resolveArgument` 는 실제로 바인딩할 객체를 리턴합니다.

```
import com.numnum.springboot.config.auth.dto.SessionUser;
import lombok.RequiredArgsConstructor;
import org.springframework.core.MethodParameter;
import org.springframework.stereotype.Component;
import org.springframework.web.bind.support.WebDataBinderFactory;
import org.springframework.web.context.request.NativeWebRequest;
import org.springframework.web.method.support.HandlerMethodArgumentResolver;
import org.springframework.web.method.support.ModelAndViewContainer;

import javax.servlet.http.HttpSession;

@RequiredArgsConstructor
@Component
public class LoginUserArgumentResolver implements HandlerMethodArgumentResolver {

    private final HttpSession httpSession;

    @Override
    public boolean supportsParameter(MethodParameter parameter) { // 컨트롤러 메소드의 특정 파라미터를 지원하는지 판단
        boolean isLoginUserAnnotation = parameter.getParameterAnnotation(LoginUser.class) != null;
        boolean isUserClass = SessionUser.class.equals(parameter.getParameterType());

        return isLoginUserAnnotation && isUserClass; // 파라미터에 @LoginUser가 붙어 있고, 클래스 타입이 SessionUser.class인 경우 true
    }

    @Override
    public Object resolveArgument(MethodParameter parameter, ModelAndViewContainer mavContainer,
                                  NativeWebRequest webRequest, WebDataBinderFactory binderFactory) throws Exception {
        return httpSession.getAttribute("user"); // 파라미터에 전달할 객체 생성
    }
}
```

**4. resolver 등록**
마지막으로 LoginUserArgumentResolver를 스프링에 등록합니다.

```
import com.numnum.springboot.config.auth.LoginUserArgumentResolver;
import lombok.RequiredArgsConstructor;
import org.springframework.context.annotation.Configuration;
import org.springframework.web.method.support.HandlerMethodArgumentResolver;
import org.springframework.web.servlet.config.annotation.WebMvcConfigurer;

import java.util.List;

@RequiredArgsConstructor
@Configuration
public class WebConfig implements WebMvcConfigurer {
    private final LoginUserArgumentResolver loginUserArgumentResolver;

    @Override
    public void addArgumentResolvers(List<HandlerMethodArgumentResolver> argumentResolvers) {
        argumentResolvers.add(loginUserArgumentResolver);
    }
}
```



