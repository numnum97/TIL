![Spring 웹 계층](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbFruEV%2FbtqAUv4HJLQ%2FH5TVBjqkKc5KBgD4Vdyvkk%2Fimg.png)</br>

### Web Layer
- 흔히 사용하는 컨트롤러(@Controller)와 JSP/Freemarker 등의 뷰 템플릿 영역
- 이외에도 필터(@Filter), 인터셉터, 컨트롤러 어드바이스(@Controller Advice) 등 **외부 요청과 응답**에 대한 전반적인 영역

### Service Layer
- @Service에 사용되는 서비스 영역
- 일반적으로 Controller와 Dao의 중간 영역에서 사용
- @Transactional이 사용되어야 하는 영역

### Repository Layer
- Database에 접근하는 영역
- Dao

### Dtos
- DTO(Data Transfer Object)는 **계층 간에 데이터 교환을 위한 객체**이고 Dtos는 이들의 영역
- 예를 들어 뷰 템플릿 엔진에서 사용될 객체나 Repository Layer에서 결과로 넘겨준 객체

### Domain Model
- **비지니스 로직**을 처리하는 영역
- 도메인이라 불리는 개발 대상을 모든 사람이 동일한 관점에서 이해할 수 있고 공유할 수 있도록 단순화시킨 것
- 예를 들어 택시 앱이면 배차, 탑승, 요금 등이 모두 도메인
- @Entity가 사용된 영역 역시 도메인 모델
- 무조건 데이터베이스의 테이블과 관계가 있어야하는 것은 아님
- VO처럼 값 객체들도 이 영역에 해당하기 때문

[출처: 스프링 부트와 AWS로 혼자 구현하는 웹 서비스](http://www.yes24.com/Product/Goods/83849117)
