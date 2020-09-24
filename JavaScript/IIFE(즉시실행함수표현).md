## 즉시 실행 함수 표현(IIFE, Immediately Invoked Function Expression)

정의되자마자 즉시 실행되는 Javascript Function 를 말한다.

```javascript
(function () {
    statements
})();
```

IIFE 내부에서 정의된 변수는 외부 범위에서 접근이 불가능하다.

IIFE를 변수에 할당하면 IIFE 자체는 저장되지 않고, 함수가 실행된 결과만 저장된다.
