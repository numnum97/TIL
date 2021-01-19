# Optional이란?
- java 8부터 도입된 클래스로 null 처리를 하지 않게끔 해주는 아주 편리한 녀석
- 제네릭을 가진 어떤 객체든 감쌀 수 있는 Wrapper 클래스
- null인지 아닌지 확신할 수 없는 객체에 대해 `ofNullable()` 메소드로 Optional 객체 생성이 가능함
- `orElse()` 메소드를 통해 null일 경우 다른 값을 반환할 수 있음
- Optional 안에 담긴 객체는 get()으로 꺼낼 수 있음
```
String text = getText();
Optional<Member> maybeText = Optional.ofNullable(text);
int length = maybeText.map(String::length).orElse(0);
```


