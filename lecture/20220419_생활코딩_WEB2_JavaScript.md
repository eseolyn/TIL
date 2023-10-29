20220419 Tue  
생활코딩  
WEB2 JavaScript  
___
27.함수 (리턴)  
함수는 입력(parameter, argument)과 출력(return)으로 이루어져 있다.  
표현식?  
1+1은 숫자 2에 대한 표현식  
2-1도 숫자 1에 대한 표현식  
1===1은 true의 표현식  

이제는 sum(2, 3);이 5가 되는 표현식으로 만들고싶다. => return  
```javascript
function sum2(left, right){
  return left+ringt;
}
```
sum2()가 계산 기능만을 구현하면서 다양한 맥락에서 활용할 수 있는 자유도가 생김  
```javascript
document.write(sum2(2,3)+'<br>');
document.write('<div style="color:red">'+sum2(2,3)+'</div>');
document.write('<div style="font-size:3rem;">'+sum2(2,3)+'</div>');
```

?? 함수의 리턴부분은 아직 궁금증이 많이 남는 파트다...  
___

28. 함수의 활용  
동작하는 내용은 같지만 코드를 효과적으로 하는 것을 __리팩토링(refactoring)__ 이라고 한다.    
onclick이벤트 안에서의 this는 이벤트가 들어간 코드(input)를 가르키기로 약속되어 있는데  
독립된 함수를 만들어 이벤트에 넣게 되면 this는 더이상 input버튼이 아닌 전역객체(?)를 가르키게 된다.  
this가 input을 가르키게 하기 위해서  
함수의 인자로 this를 주고 매개변수로 self를 준다.  
함수 안의 this들을 self로 바꾼다.  
___
29. 객체(object) 예고  
객체? 서로 연관된 함수와 변수들을 그룹화해서 정리정돈하기위한 수납상자  
disk의 directory,folder같은 역할  
객체를 도입하면 객체를 사용하는 쪽의 코드는  
예) Body라는 객체를 만들고 객체 뒤에 점.을 찍어 Body.setColor('white')와 같은 형식으로 만들 수 있다.  
document.querySelector('body')에서 보듯이  
document는 객체이고 querySelector는 객체에 속해있는 함수이다.  
그리고 이 객체에 속해있는 함수를 __메소드__ 라고 부른다.  

30. 객체의 쓰기와 읽기  
[배열] = 순서에 따라 정보들을 저장하는 그릇  
{객체} = 순서가 아닌 이름이 있는 정리 정보를 저장  
```javascript
var coworkers = {
  "programmer":"egoing",
  "designer":"leezche"
};
document.write("programmer : "+coworkers.programmer+"<br>");
document.write("designer : "+coworkers.designer+"<br>");
coworkers.bookkeeper = "duru";
document.write("bookkeeper : "+coworkers.bookkeeper+"<br>");
// 객체 이름에 띄어쓰기가 있어 점.을 사용할 수 없을 때 
coworkers["data scientist"] = "taeho";
document.write("data scientist : "+cowork때ers["data scientist"]+"<br>");
```
이렇게 객체 생성, 객체에서 데이터 가져오기, 객체에 데이터 넣기를 할 수 있다.  
___
31. 객체와 반복문(iterate)  
객체의 정보를 모두 가져와야 할 때? 
```
for(var key in coworkers) {
  document.write(key+' : '+coworkers[key]+'<br>');
}
```
이렇게 쓰면 30.에서 썼던 코드와 같은 결과가 나오면서 모든 데이터 순회해 확인할 수 있다.  
___
32. 객체프로퍼티와 메소드  
객체에는 문자, 숫자, 배열같은 모든 데이터와 함께 함수도 담을 수 있다.  
coworkers의 메소드를 만들어보자  
```javascript
coworkers.showAll = function(){
// 이부분은 function showAll(){}과 같은 표현이다.
	for(var key in this) {
		document.write(key+' : '+this[key]+'<br>');
	}
}
// showAll()또한 객체에 포함되어 있기 때문에 결과에 같이 나타난다.
```
객체에 소속된 함수를 method라 하고  
객체에 소속된 변수를 property라 한다.  
___
33. 객체의 활용
```javascript
function BodySetColor(color){
    document.querySelector('body').style.color = color;
  }
  function BodySetBackgroundColor(color){
    document.querySelector('body').style.backgroundColor = color;
```
-->
```javascript
var Body = {
    setColor:function (color){
      document.querySelector('body').style.color = color;
    }, 
// 프로퍼티 사이에 쉼표,필요
    setBackgroundColor:function (color){
      document.querySelector('body').style.backgroundColor = color;
    }
function nightDayHandler(self){
	var target = document.querySelector('body');
	if(self.value === 'night'){
		Body.setBackgroundColor('black');
		Body.setColor('white');
		self.value = 'day';
	} else {
		Body.setBackgroundColor('white');
		Body.setColor('black');
		self.value = 'night';
	}
}
```
