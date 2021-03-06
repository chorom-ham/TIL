## HTTP란?

HTTP(HyperText Transfer Protocol)는 WWW 상에서 정보를 주고받을 수 있는 프로토콜이다. 

주로 HTML 문서를 주고받는 데에 쓰인다. Plain text로 부터 JSON 데이터 및 XML과 같은 형태의 정보도 주고 받을 수 있으며, 보통은 클라이언트가 어떤 정보를 HTML 형태로 받고 싶은지, JSON 형태로 받고 싶은지 명시해주는 경우가 많다.

응용 계층(Application layer)의 프로토콜이다.

HTTP는 클라이언트와 서버 사이에 이루어지는 요청/응답(request/response) 프로토콜이다. 

항상 연결 상태를 유지하는 것이 아니라 요청/응답 시에만 통신한다.(비연결성 프로토콜)

## 동작 예시

클라이언트인 웹 브라우저가 HTTP를 통하여 서버로부터 웹페이지(HTML)나 그림 정보를 요청하면, 서버는 이 요청에 응답하여 필요한 정보를 해당 사용자에게 전달하게 된다. 

이 정보가 모니터와 같은 출력 장치를 통해 사용자에게 나타나는 것이다.

HTTP를 통해 전달되는 자료는 http:로 시작하는 URL(인터넷 주소)로 조회할 수 있다.

서버는 클라이언트의 요청에 대한 응답을 보내주는(어떠한 자료에 대한 접근을 관리하는) 네트워크 상의 시스템이다.

서버와 클라이언트 사이에 요청/응답을 주고 받을 때, 즉 통신할 때 아무런 규칙없이 요청과 응답을 보내면 서로 이해할 수 없으니 하나의 규칙을 정한 것이다.

그것이 바로 HTTP이다.

해당 규약, 서로 주고 받는 메시지 포맷은 https://ko.wikipedia.org/wiki/HTTP 여기서 확인할 수 있다. 

웹 개발을 할 때 필요한 지식이므로 알아두도록 하자.
