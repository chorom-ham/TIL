## Java에서의 this와 다르다!

Java에서의 this는 인스턴스 자신(self)을 가리키는 참조변수이다. 

this가 객체 자신에 대한 참조 값을 가지고 있다는 뜻이다. 

주로 매개변수와 객체 자신이 가지고 있는 멤버변수명이 같을 경우 이를 구분하기 위해서 사용된다. 

하지만 자바스크립트의 경우 Java와 같이 this에 바인딩되는 객체는 한가지가 아니라 해당 함수 호출 방식에 따라 this에 바인딩되는 객체가 달라진다.

(헷갈리면 그냥 화살표 함수를 쓰자....화살표 함수 최고)

<br/>

## 함수 호출 방식과 this 바인딩

자바스크립트의 경우 함수 호출 방식에 의해 this에 바인딩할 어떤 객체가 동적으로 결정된다. 

다시 말해, 함수를 선언할 때 this에 바인딩할 객체가 정적으로 결정되는 것이 아니고, 함수를 호출할 때 함수가 어떻게 호출되었는지에 따라 this에 바인딩할 객체가 동적으로 결정된다.

함수의 호출하는 방식은 아래와 같이 다양하다.

1. 함수 호출

2. 메소드 호출
3. 생성자 함수 호출
4. apply/call/bind 호출

```javascript
var foo = function () {
  console.dir(this);
};

// 1. 함수 호출
foo(); // window
// window.foo();

// 2. 메소드 호출
var obj = { foo: foo };
obj.foo(); // obj

// 3. 생성자 함수 호출
var instance = new foo(); // instance

// 4. apply/call/bind 호출
var bar = { name: 'bar' };
foo.call(bar);   // bar
foo.apply(bar);  // bar
foo.bind(bar)(); // bar
```
## 1. 함수 호출

기본적으로 this는 전역객체(Global object)에 바인딩된다. 

전역객체(Global Object)는 모든 객체의 유일한 최상위 객체를 의미하며 일반적으로 Browser-side에서는 window, Server-side(Node.js)에서는 global 객체를 의미한다.

전역함수는 물론이고 심지어 내부함수의 경우도 this는 외부함수가 아닌 전역객체에 바인딩된다.

내부함수는 일반 함수, 메소드, 콜백함수 어디에서 선언되었든 관게없이 this는 전역객체를 바인딩한다. 

## 2. 메소드 호출

함수가 객체의 프로퍼티 값이면 메소드로서 호출된다. 이때 메소드 내부의 this는 해당 메소드를 소유한 객체, 즉 해당 메소드를 호출한 객체에 바인딩된다. (프로토타입 객체도 마찬가지)

## 3. 생성자 함수 호출

new 연산자와 함께 생성자 함수를 호출하는 경우, 생성자 함수 내부의 this는 생성자 함수에 의해 생성된 인스턴스를 가리킨다.

new 연산자를 빼먹는 경우 전역변수에 바인딩 된다.

## 4. apply/call/bind 호출

this에 바인딩될 객체는 함수 호출 패턴에 의해 결정된다. 이는 자바스크립트 엔진이 수행하는 것이다. 

이러한 자바스크립트 엔진의 암묵적 this 바인딩 이외에 this를 특정 객체에 명시적으로 바인딩하는 방법도 제공된다. 

이것을 가능하게 하는 것이 Function.prototype.apply, Function.prototype.call 메소드이다.



출처: https://poiemaweb.com/js-this
