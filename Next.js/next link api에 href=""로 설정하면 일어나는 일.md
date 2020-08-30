## next link api에 href=""로 설정하면 일어나는 일

현재 url의 pathname으로 이동한다.

쿼리스트링은 유지되지 않는다.

### Example

```
import Link from "next/link";

export default function Example(){
  return(
    <Link href=""><a>example</a></Link>
  );
}
```
현재 url : https://github.com/chorom-ham/TIL/query?yes&foo?bar 에서 example 링크를 눌렀을 때

<b>https://github.com/chorom-ham/TIL/</b>로 라우팅된다.
