20220324 thu
nomadcoder
ReactJS Movie Web Service
#6.0 ~ 6.2 : Effects


#6.0
섹션 6에서는 state와 props에 이어 마지막으로 중요한 또 하나 effect를 배울 것

다시한번 react가 어떻게 작동하는지 보자
이미 react에서 만든 app이기때문에 useState 앞에 react. 을 쓸 필요가 없다.

```
import { useState } from "react";

function App() {
  const [counter, setValue] = useState(0);
  const onClick = () => setValue((prev) => prev + 1);
  return (
    <div>
      <h1>{counter}</h1>
      <button onClick={onClick}>Click me</button>
    </div>
  );
}

export default App;
```
useState를 통해 state를 받아 +1하는 onClick 함수를 만들었고
state를 modify할 수 있도록 하는 버튼도 만든다. 
버튼을 눌러 함수를 작동시킨 값을 h1의 counter를 통해 보여준다.

render될 때를 console.log 해보면 처음 시작할 때와 버튼을 누를 때마다 render되는 것을 볼 수 있다.
버튼을 누를때마다 전체가 새로 불러와지고 있다.

하지만 매번 전체를 불러오는게 아닌 처음 render될 때만 코드가 실행되고, 
다른 state변화에는 실행되지 않도록 원할 수도 있다.
ex) api를 통해 데이터를 받아오고 이후에 state가 변화할 때마다 그api에서 데이터를 또 가져오고 싶진 않다.

우리는 어떻게 특정 코드가 첫번째 component render에만 실행되고 
그 후 state변화에는 실행되지 않게 할 수 있는지 알고싶다.

#6.1 useEffect
이러한 고민을 가진 우리를 위한 react 기능! useEffect
useEffect는 두 개의 argument(인자)를 가지는 함수다.
function useEffect(effect: EffectCallback, deps?: DependencyList): void
첫번째 인자가 딱 한번만 실행하고 싶은 코드

```
const onClick = () => setValue((prev) => prev + 1);
  console.log("i run all the time");
  const iRunOnlyOnce = () => {
    console.log("i run only once");
  };
  useEffect(iRunOnlyOnce, []);
```
((왜 코드변경된게 바로 적용이 안되는거지...? 캐시비우기 및 강제 새로고침해도 안되네ㅠㅠ))
component의 첫 번째 render에서 useEffect가 함수를 불러 콘솔에 두 문장이 찍히게 된다.
이 상태에서 버튼을 눌러 state를 변화시켜보면 i run all the time만 찍힌다.
useEffect의 첫번째 인자로 불러온 함수는 다시 실행되지 않는거다.
코드가 딱 한번만 실행될 수 있도록 보호해준다.

#6.2 Deps
useEffect의 두번째 인자 Deps를 알아보기 위해 검색창을 하나 만들어보자
```
function App() {
  const [counter, setValue] = useState(0);
  const [keyword, setKeyword] = useState("");
  const onClick = () => setValue((prev) => prev + 1);
  const onchange = (event) => setKeyword(event.target.value);
  console.log("i run all the time");
  useEffect(() => {
    console.log("CALL THE API...");
  }, []);
  console.log("SEARCH FOR", keyword);
  return (
    <div>
      <input
        value={keyword}
        onChange={onchange}
        type="text"
        placeholder="Search here..."
      />
      <h1>{counter}</h1>
      <button onClick={onClick}>Click me</button>
    </div>
  );
}
```
인풋창에 키워드를 쓰면 onchange함수 활성화되면서 입력값을 반환해 콘솔에 찍을 수 있음
i run all the time
SEARCH FOR ~~

문제는 counter버튼을 누를때마다 또 onchange가 활성화 된다.

이제는 내 코드의 특정한 부분만이 변화했을 때, 
원하는 코드를 실행할 수 있는 방법을 배우고싶다.

즉, 인풋창 state가 변화할 때만 검색하고 싶다. (버튼 누를 때 말고!)

useEffect를 하나 추가해보자
```
useEffect(() => {
    if (keyword !== "" && keyword.length > 5) {
      console.log("SEARCH FOR", keyword);
    }
  }, [keyword]);
```
=keyword가 변화할 때, keyword가 공백이 아니고 5글자 이상이면 이 코드(console.log)를 실행해!
라는 명령이 된다.
