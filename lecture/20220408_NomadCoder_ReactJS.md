20220408 Fri  
Nomad Coders  
Movie web service  

오늘 할 일  
Coin Tracker 복습  
목표: 코인 정보 리스트 만들기  
___
1. 2개의 state  
: 하나는 로딩, 하나는 코인리스트를 잠시 갖고 있기 위한 것  

strong태그 : 굵은 강조 글씨체  
fetch().then() : fetch를 로드하는동안 then을 실행  
.then(function(response) : 콜백함수  
: JS는 브라우저에서 작동하기 때문에, 브라우저는 서버가 응답을 보내는 동안 다른 작업을 수행해야하므로  
일부 원격 작업이 완료되면 콜백을 사용하여 코드를 다시 호출한다. (생활코딩 Ajax참조)  
*return response.json()  
  
=> 이게 기본형태  
```html
fetch(API).then(function(response){
  return response.json();
  }).then(function(json){
  json내부값 활용})
```
ul태그 : unordered list의 줄임말, 순서가 없는 목록으로 글머리 기호를 붙여 목록을 만든 형식  
___
2. 로딩중 코인목록을 불러옴, 불러온 목록을 state에 넣어 .map으로 UI에 그려주고 로딩을 끝냄  
  
map을 사용하면 react.js는 element에 key를 줘야한다. 이번 코인목록에는 id가 있기때문에 따로 index를 주지 않아도 된다.  
