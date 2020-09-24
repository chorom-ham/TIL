## async&await 방식

간단하고 직관적으로 비동기 처리를 할 수 있는 방식이다.

## 기본 문법

```javascript
async function 함수명() {
  await 비동기_처리_메서드_명();
}
```

먼저 함수의 앞에 async 라는 예약어를 붙이고, 함수의 내부 로직 중 HTTP 통신을 하는 비동기 처리 코드 앞에 await를 붙인다. 

*주의* 비동기 처리 메서드가 꼭 프로미스 객체를 반환해야 await가 의도한 대로 동작한다.

일반적으로 await의 대상이 되는 비동기 처리 코드는 Axios 등 프로미스를 반환하는 API 호출 함수다.

await 처리되는 비동기 처리 코드가 수행 완료 된 다음, 다음 코드가 실행된다

## 예외 처리 방법

try-catch 사용
