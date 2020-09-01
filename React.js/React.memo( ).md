## React.memo()란?

React는 먼저 컴퍼넌트를 렌더링(rendering) 한 뒤, 이전 렌더된 결과와 비교하여 DOM 업데이트를 결정한다. 만약 렌더 결과가 이전과 다르다면, React는 DOM을 업데이트한다.

다음 렌더링 결과와 이전 결과의 비교는 빠르다. 하지만 어떤 상황에서는 이 과정의 속도를 좀 더 높일 수 있다.

컴퍼넌트가 React.memo()로 래핑 될 때, React는 컴퍼넌트를 렌더링하고 결과를 메모이징(Memoizing)한다. 

그리고 다음 렌더링이 일어날 때 props가 같다면, React는 메모이징(Memoizing)된 내용을 재사용한다.


## 2. React.memo()를 사용하는 것이 좋은 경우

- 같은 props로 렌더링이 자주 일어나는 컴퍼넌트

React.memo()는 함수형 컴퍼넌트에 적용되어 같은 props에 같은 렌더링 결과를 제공한다.

React.memo()를 사용하기 가장 좋은 케이스는 함수형 컴퍼넌트가 같은 props로 자주 렌더링 될거라 예상될 때이다.

일반적으로 부모 컴퍼넌트에 의해 하위 컴퍼넌트가 같은 props로 리렌더링 될 때가 있다.

위 경우가 아니라면 굳이 사용할 이유가 없다.

### 참고한 링크

- https://react.vlpt.us/basic/19-React.memo.html

- https://ui.toast.com/weekly-pick/ko_20190731/
