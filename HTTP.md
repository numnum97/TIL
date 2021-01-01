REST API에 대해서 공부하던 중에 HTTP라는 용어를 보고
이게 뭐지(?)라고 떠올린 자신을 보고 먼저 이렇게 HTTP에 대해 정리해보겠습니다.
관련된 AJAX와 웹소켓에 대해서도 뒤이어 정리할 예정입니다 :)

출처는 [Chullin님의 Medium](https://medium.com/@chullino/http%EC%97%90%EC%84%9C%EB%B6%80%ED%84%B0-websocket%EA%B9%8C%EC%A7%80-94df91988788)

# HTTP란?
-Hyper Text Transfer Protocol의 약자로서 텍스트 문서를 교환하기 위한 약속으로
1989년에 팀 버너스리 아저씨에 의해서 고안되었습니다.

-그전까지는 터미널에서 텍스트로만 통신을 하다가, gif같은 이미지도 바로 볼 수 있게 되었습니다.

-Transfer Protocol이라는 말 그대로 HTTP는 **URL** 및 부가정보를 통해 사용자가 원하는 페이지를 서버에 **요청**하고, 서버가 응답하는 방식으로 이루어집니다.

![이렇게 요청을 하면 서버에 의해 새로운 페이지로 이동하게 됨](https://miro.medium.com/max/700/1*osHAtlS5u-1fX1KPqo0bCg.jpeg)
[출처](https://hieroglyph.tistory.com/13)

-이렇게 사용자가 항상 새로운 정보를 위해서는 반드시 새로운 URL을 요청해야 하는데..

-그 예시가 우리가 그토록 혐오하는 Active X입니다.

-이 HTTP의 불편함을 해소하고자 Google에서 만든 것이 바로 AJAX입니다.
