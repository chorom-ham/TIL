## d.ts 파일?
d.ts 파일은 타입스크립트 선언 파일이다. 타입스크립트 코드의 타입 추론을 돕는다.

전역 변수로 선언한 변수를 특정 파일에서 import 구문 없이 사용하는 경우 해당 변수를 인식하지 못한다. 

그럴 때 아래와 같이 해당 변수를 선언해서 에러가 나지 않게 할 수 있다.

```
declare const global = 'sth';
```

## 전역 변수와 전역 함수에 대한 타입 선언
해당 타입스크립트 파일에서 사용할 순 있지만 선언되어 있지 않은 전역 변수나 전역 함수는 아래와 같이 타입을 선언할 수 있다.
```
// 전역 변수
declare const pi = 3.14;

// 전역 함수
declare namespace myLib {
  function greet(person: string): string;
  let name: string;
}
myLib.greet('캡틴');
myLib.name = '타노스';
```

출처: https://joshua1988.github.io/ts/usage/declaration.html#%ED%83%80%EC%9E%85%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EC%84%A0%EC%96%B8-%ED%8C%8C%EC%9D%BC
