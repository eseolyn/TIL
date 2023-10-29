20220328 mon
Nomad Coders

#7.0 ~ 7.1 To Do List

이제 이론은 끝! 실전 연습만 남았다.
여태 배운 state, props, Effect 를 이용해 to do list를 만들어본다.

버튼을 누르면 인풋이 사라져 새로고침되는데
그 form 안에 button이 하나만 있다면 버튼을 클릭했을 때 form을 submit하기때문 (form의 기본 기능)


array를 직접적으로 수정하지 않으면서 setToDos로 array에 element를 추가하는 방법 =
절대! state를 직접적으로 수정하지 않는다! 항상 수정하는 함수(set~)를 사용한다.

#7.3~7.6

오늘 메모(배운 이론, 오류수정 등등)
#7.3~7.4 Movie App
coin Tracker 복습수준
then. 대신 async await 함수가 더 깔끔?
oldArray.map(item => how) ===> newArray

API에서 받는 데이터 이름은 바꾸면 안되지만 component간 데이터를 연결해주는 props의 이름은 API내 이름과 같을 필요는 없다.


#7.5 React Router
router는 URL을 보고있는 component고
URL에 따라 Home 또는 Detail페이지를 보여줄 것이다.

Router를 이용해 누군가 만들어 놓은 컴포넌트를 그냥 사용하기만 하면 되고
Switch는 Route를 찾고 컴포넌트를 렌더링하는 일을 한다. (Route는 URL의 / 뒷부분 주소)


#7.6 Parameters
React Router는 동적URL을 지원해준다.
동적이라는것은 URL에 변수를 넣는 것이 가능하다는 뜻이다.
"/movie/:id"로 쓰면 /뒤에 변수를 넣을 수 있다. :를 꼭 써야한다!

Home.js
```
{movies.map((movie) => (
            <Movie
              key={movie.id}
              id={movie.id}
...
```
Movie가 prop으로 id를 받고있기에 Movie.js에서 id를 받아 proptypes를 설정
props는 object일 뿐이고, 우리는 그걸 열어서 item을 꺼내 쓰는것!


(warning: React Hook useEffect has a missing dependency: 'getMovie'. Either include it or remove the dependency array.)
=> useCallback을 쓰라는 댓이 있는데 잘 모르겠다@.@;;

내일 해야 할 것
섹션7 끝내기 
7.3 & 7.6복습필수;;

느낀점
역시 이론만으로는 부족해 연습을 해봐야 제대로 공부가 안됐다는걸 확실히 알 수 있지ㅋ
