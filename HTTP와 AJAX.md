REST API에 대해서 공부하던 중에 HTTP라는 용어를 보고
이걸 정확히 설명할 수 있을까(?)라고 떠올린 자신을 보고 먼저 이렇게 HTTP에 대해 정리해보겠습니다.
관련된 AJAX와 웹소켓에 대해서도 뒤이어 정리할 예정입니다 :)

출처는 [Chullin님의 Medium](https://medium.com/@chullino/http%EC%97%90%EC%84%9C%EB%B6%80%ED%84%B0-websocket%EA%B9%8C%EC%A7%80-94df91988788)

# HTTP란?
- Hyper Text Transfer Protocol의 약자로서 텍스트 문서를 교환하기 위한 약속으로
1989년에 팀 버너스리 아저씨에 의해서 고안되었습니다.

- 그전까지는 터미널에서 텍스트로만 통신을 하다가, gif같은 이미지도 바로 볼 수 있게 되었습니다.

- Transfer Protocol이라는 말 그대로 HTTP는 **URL** 및 부가정보를 통해 사용자가 원하는 페이지를 서버에 **요청**하고, 서버가 응답하는 방식으로 이루어집니다.

![이렇게 요청을 하면 서버에 의해 새로운 페이지로 이동하게 됨](https://miro.medium.com/max/700/1*osHAtlS5u-1fX1KPqo0bCg.jpeg)
[출처: Chullin님의 Medium](https://medium.com/@chullino/http%EC%97%90%EC%84%9C%EB%B6%80%ED%84%B0-websocket%EA%B9%8C%EC%A7%80-94df91988788)

- 이렇게 사용자가 항상 새로운 정보를 위해서는 반드시 새로운 URL을 요청해야 하는데..

- 그 예시가 우리가 그토록 혐오하는 Active X입니다.

- 이 HTTP의 불편함을 해소하고자 **Google**에서 만든 것이 바로 비동기 통신 AJAX입니다.


# AJAX(Asynchronous Javascript And Xml)

- HTTP를 효과적으로 이용하는 기술로 새로운 웹페이지로 이동하는 것이 아니라, 동일한 웹페이지 안에서 DOM을 변경하게 됨.

![AJAX를 도입한 HTTP 통신](https://miro.medium.com/max/650/1*pND1GyjbfxlGmUuqylVoZw.jpeg)
[출처: Chullin님의 Medium](https://medium.com/@chullino/http%EC%97%90%EC%84%9C%EB%B6%80%ED%84%B0-websocket%EA%B9%8C%EC%A7%80-94df91988788)

- 사용자의 이벤트로부터 Javascript는 그 DOM을 읽고 XMLHttpRequest를 통해 서버에 전송하고 생성된 XML, Text, JSON을 다시 XMLHttpRequest에 전송하면 Javascript가
DOM에 써서 결과페이지를 만든다.

- 즉, 사용자 입장에서는 페이지를 이동하지 않고 페이지 내부 변화만 경험하게 됩니다.

- 그에 따라, 다음과 같은 장점이 발생하게 됩니다. XMLHttpRequest 객체를 통해 서버에 request하기 때문에 서버와 연결이 끊기지 않은 상태로 JSON이나 XML형태로 필요한 데이터만 DOM을 갱신하며 주고 받아 자원과 시간을 아낄 수가 있습니다.

- 아이디 중복확인, 비밀번호 강도 확인, 검색어 실시간 추천, 지도 표시 서비스 등이 이와 같은 AJAX의 장점을 보여주는 사례라고 할 수 있습니다.

![](https://image.slidesharecdn.com/111015-111017005159-phpapp02/95/111015-html5-1-23-728.jpg?cb=1327713875)
[출처: HTML5를 여행하는 비(非) 웹 개발자를 위한 안내서](https://www.slideshare.net/hiscale/111015-html5-1)

- 위와 같이 서버가 요청하지 않은 응답은 보내줄 수가 없다는 한계가 발생합니다.

- 이와 같은 한계가 HTML5 개발 과정에서 해결되었고, 그것이 바로 **웹소켓**입니다.

# 웹 소켓(Web Socket)

- HTTP와 같은 프로토콜로서 양방향 통신을 할 수 있도록 지원합니다.

- 전과 같이 클라이언트의 요청이 없는 경우 서버가 응답을 못하는 것이 아니라, 서버도 자유롭게 브라우저에 데이터를 보낼 수 있게 되었습니다.

- 웹에서됴 채팅, 게임, 주식 등 실시간 정보 교환이 요구되는 응용 프로그램의 개발도 한층 효과적으로 구현이 가능해졌습니다.



