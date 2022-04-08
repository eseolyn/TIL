20220407 Thu  
Nomad Coders  
Movie web service  

오늘 할 일  
1. Todo List  

___
Todo List 복습  
목표:  
1. 인풋과 인풋값 찾기: useState()  
2. 폼에 넣어 submit기능 사용  
3. Todo array 만들기:  
```
[...currentArray]  
```
4. Todo를 UI에 나타내기:  
```
toDos.map((item, index) => <li key={index}>{item}</li>)  
```

? preventDefault()  
a 태그나 submit 태그는 누르게 되면 href를 통해 이동하거나, 창이 새로고침하여 실행됩니다.  
preventDefault를 통해 이러한 동작을 막아줄 수 있습니다.  
주로 사용되는 경우는  
1. a 태그를 눌렀을때도 href 링크로 이동하지 않게 할 경우  
2. form 안에 submit 역할을 하는 버튼을 눌렀어도 새로 실행하지 않게 하고싶을 경우 (submit은 작동함)  
