20220404 mon  
Nomad Coders  
ReactJS movie web service  
#3 복습  
___
vanilaJS에서는 버튼을 누르면 바로 업데이트가 되지만 body전체가 리렌더링 된다.  
ReactJS에서는 바뀐 부분(count)만 업데이트 해준다.  
리액트는 렌더된 컴포넌트와 다음 컴포넌트를 비교해 다른 부분만 파악해 업데이트한다.  
  
초기 컴포넌트가 초기 데이터를 가지고 렌더링되고  
우리가 버튼을 누르면 다시 렌더링 하고 싶은것  
리렌더링을 유발시키는 ReactJS 기능을 사용  
  
useState를 사용하면 배열이 나오는데 그 배열의 첫번째 요소는 데이터 초기값이고  
두 번째 요소는 그 값을 바꾸는 함수(modifier)다.  
배열의 요소들을 꺼내는 법  
[첫요소이름, 둘째요소이름] = useState  
  
왜 modifier가 필요한가?  
리렌더링 코드를 매번 직접 넣어줄 필요 없이 데이터를 변경시켜주고 자동으로 리렌더링 해준다.  
보통 modifier에는 set뒤에 데이터 이름을 붙인다.(setCounter)  
modifier함수를 이용해 컴포넌트의 state를 바꿀 때 컴포넌트는 새로운 값을 가지고 다시 렌더링된다.  

```
const [counter, setCounter] = React.useState();
      const onClick = () => {
        setCounter(counter + 1);
      };
```
  
state를 세팅하는데 2가지 방법이 있다.  
1. modifier에 직접 값을 설정하는 것  
2. " 함수 전달하기  
현재 값을 가지고 계산을 해야 버그가 생길 확률을 줄일 수 있다.  
modifier에 함수를 넣을 수 있는데 이 함수의 첫째 인자(argument)는 현재 값이다.  
그리고 이 함수의 return값이 새로운 state가 된다.  
setCounter((current) => current + 1);  
이런 식을 쓰는것이 current가 확실히 현재 값이라는걸 보장하고 있기때문에 더 안전하다.  
  
#3.5 make converter!  
label태그: input옆에 써주는 글씨로 누르면 그 옆 input이 선택됨  
JSX에서는 class대신 className, for대신 htmlFor을 쓴다.  
  
state로써 minutes라는 값을 가지고 있는데 이 값을 input의 value로 넣고싶다.  
input에 변화(입력)가 생길 때마다 변화를 리스닝하기위해 onChange함수 사용  
```
const onChange = (event) => {
        setMinutes(event.target.value);
      };
```
