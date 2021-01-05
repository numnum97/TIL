# Bean
- Bean은 Spring IoC Container가 관리하는 자바 객체, Spring Bean Container에 존재하는 객체이다. </br>
- Spring IoC Container에 의해 인스턴스화, 관리, 생성된다.</br>
- Spring에서 Bean은 보통 Singleton으로 존재한다.
##### Singleton: 어떤 Class가 최초 한번만 메모리를 할당하고(Static) 그 메모리에 객체를 만들어 사용하는 디자인 패턴

![Bean](https://media.vlpt.us/images/gillog/post/2af99237-b71c-45ae-87f2-84ad73f72f3e/spring-bean.png)

- Beans는 Application의 핵심을 이루는 객체이며, 대부분 Container에 공급하는 메타 데이터(XML)에 의해 생성된다.</br>
- Container는 이 메타 데이터를 통해 Bean의 생성, Bean Life Cycle, Bean Dependency 등을 알 수 있다.</br>
- new로 생성하는 객체는 Bean이 아니고, Application.getBean()으로 얻어질 수 있는 객체는 Bean이다.</br>
- 즉, **Spring에서의 Bean은 ApplicationContext가 알고있는 객체, 그 안에 만들어서 담고 있는 객체**를 뜻한다.

[출처: gilLog님의 Velog](https://velog.io/@gillog/Spring-Bean-%EC%A0%95%EB%A6%AC)


