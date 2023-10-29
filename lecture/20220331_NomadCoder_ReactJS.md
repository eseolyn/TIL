20220331 thu  
Nomad Coders  
ReactJS movie web service  
#2 복습
___
오늘 메모  
#2  
react는 App이 interactive하게 만들어주는 library이고   
react-dom은 library또는 package인데 모든 react Elements를 HTML body에 둘 수 있도록 해준다.  

body에 빈 div를 만들고 이 div에 ReactDOM이 React Elements를 가져다 놓는다.  
```
<body>
  <div id="root"></div>
</body>
<script>
  const root =document.getElementById("root")
</script>
```
#2.3은 사용하지는 않지만 이해하기 위한 코드를 배움  

#2.5 JSX  
JSX는 JavaScript를 확장한 문법인데 HTML과 문법이 비슷해 사용하기 편하다.  
```
const ... = <tag props>content</tag>
```
브라우저가 JSX를 알아듣기 위해서 Babel standalone 이라는 변환기를 설치하고 script에 type을 넣어준다.  

#2.6  
코드를 Arrow function =()=> 으로 만든 후 render될 컴포넌트에 <Title />과 같은 형식으로 넣는다.  
첫글자는 대문자로! HTML태그는 소문자, 직접 생성한것은 대문자  
  
  ___
복습하려다보니 #2까지 내려와버렸다...  
