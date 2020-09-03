같은 컴포넌트들을 정렬해서 보여줄 때 기존에는 배열을 슬라이스해서 row안에 정해진 수만큼 들어가게 구현했다.

예시)
```
const getList = (items) => {
    return (
      <>
        <Row>{items.slice(0, 3).map(getBlock)}</Row>
        <Row>{items.slice(3, 6).map(getBlock)}</Row>
        <Row>{items.slice(6, 9).map(getBlock)}</Row>
        <Row>{items.slice(9, 12).map(getBlock)}</Row>
        <Row>{items.slice(12, 15).map(getBlock)}</Row>
      </>
    );
  };
  ```

하지만 이 경우, 배열의 길이가 달라지면 모든 아이템들이 보여지지 않았다.

배열의 길이가 동적으로 변할 때 감싸고 있는 div의 width를 넘어서 삐져나간 것처럼 보이지 않고 자동으로 다음 줄로 내려가게 하는 방법을 고민했다.

### 해답은 flex-wrap 속성 설정이었다.

flex-wrap은 flex item이 flex container를 벗어났을 때 줄을 바꾸는 속성이다. white-space 속성과 동일하게 작동한다. 

속성의 기본값인 nowrap은 flex item의 전체 크기가 flex container보다 커져도 줄을 바꾸지 않고 한 줄로 flex item을 배치한다.

### flex-wrap: wrap 속성은 flex item의 전체 크기가 flex container보다 크면 줄을 바꿔 여러 줄로 flex item을 배치한다.

```
.flex_container {
  display: flex;
  flex-flow: row wrap;
  ...
}
```
위와 같이 코드를 짜면

1 2<br/>
3 4<br/>
5 6<br/>
.<br/>
.<br/>
.<br/>
이런식으로 아이템들이 배치된다.
