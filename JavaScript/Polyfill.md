## Polyfill 이란?
직역하면 충전재라는 뜻.

웹 개발에서 기능을 지원하지 않는 웹 브라우저 상의 기능을 구현하느 코드를 뜻한다.

기능을 지원하지 않는 브라우저에서 마치 충전재와 같은 역할을 하는 것이다.

단점은 폴리필 플러그인 로드로 인해 시간과 트래픽이 늘어나고, 성능이 저하되는 것이다.

 - 새로 추가된 전역 객체들(Promise, Map, Set)을 사용가능한 객체로 바꾸어주는 개념

 - 브라우저 파편화를 해결하기 위해 지원하지 않는 공백을 매꾸는 스크립트나 기타 코드를 끼워넣어줌


## Babel과의 차이점
- Babel: Javascript 의 Syntax 가 아닌 것들을 Javascript 에서 사용할 수 있게 만들어 줌
- Polyfill: Javascript 의 Syntax 로 읽히지만 정의되어 있지 않은 객체들을 정의해주는 개념


 예를들어 Promise 객체는 기존에 존재하지 않는 ES6 에서 추가된 객체로, ES6 이전에서 new Promise() 를 하는 경우 Javascript 의 Syntax 이지만 정의되지 않는 function 이라는 의미에서 'Promise is not a function' 의 결과를 보여준다. Polyfill 개념을 이용해 Promise 를 사용할 수 있도록 정의해주는 것을 Babel-Polyfill 이 해줄 수 있다. (은져미 블로그)

해당 설명을 보고나니 자바스크립트 함수의 문제라기 보다는 es6에서 새로 생긴 Map과 Set, promise 객체를 ie에서는 지원을 하지 않아 오류가 났고, polyfill이 이를 정의해줌으로써 ie에서도 정상적으로 작동이 된 것 같다.

출처: https://jcon.tistory.com/123
