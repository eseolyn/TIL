20220325 fri
nomadcoder
ReactJS Movie Web Service
#6.3 ~ 6.4 : Effects

#6.3 recap
useEffect는 두개의 argument를 가지는 함수
첫번째 인자는 내가 실행시키고 싶은 코드
두번째 인자는 dependencies = react.JS가 지켜보다 변화가 일어나면 react.JS가 코드를 실행시킴

```
import { useState, useEffect } from "react";

function App() {
  const [counter, setValue] = useState(0);
  const [keyword, setKeyword] = useState("");
  const onClick = () => setValue((prev) => prev + 1);
  const onChange = (event) => setKeyword(event.target.value);
  useEffect(() => {
    console.log("I run only once.");
  }, []);
  useEffect(() => {
    console.log("I run when 'keyword' changes.");
  }, [keyword]);
  useEffect(() => {
    console.log("I run when 'counter' changes.");
  }, [counter]);
  useEffect(() => {
    console.log("I run when keyword & counter change");
  }, [keyword, counter]);
  return (
    <div>
      <input
        value={keyword}
        onChange={onChange}
        type="text"
        placeholder="Search here..."
      />
      <h1>{counter}</h1>
      <button onClick={onClick}>click me</button>
    </div>
  );
}

export default App;
```
첫번째 예시를 보면 인자1만 있고 인자2는 없다
즉 리액트가 지켜볼 대상이 없기 때문에 코드가 한번만 실행될 것임
두번째 예시를 보면 인자2에 [키워드]가 있다. 인풋에 변화가 일어날 때 온체인지->셋키워드->키워드 순으로 연결되어 인자2[키워드]에 변화가 감지, 인자1 함수가 실행된다.
인자2에는 두개 이상의 인자를 arrey형태로 넣는것도 가능하다. 네번째 예시처럼


# 6.4 cleanup
(잘 사용하는 것은 아니지만...)
```
function Hello() {
  useEffect(() => {
    console.log("created :)");
    return () => console.log("destroyed :(");
  }, []);
  return <h1>Hello</h1>;
}
```
show버튼을 눌러 hello문장을 create! 다시 누르면 destroy
react.js는 component가 destroy될 때도 코드를 실행할 수 있다! useEffect를 이용해서!
useEffect의 인자1에 return함수를 하나 만든다. hide버튼을 눌러 destroy될 때 이 return함수가 실행된다.간단?
