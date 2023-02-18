## for()  
`for ( 초기화식; 조건식; 증감식 ){ 실행문; }`  
- 조건식이 true일 동안 순회  
- 멈추고 싶다면 break; 사용  

`for ( property in object ){ 실행문; }`  
- 모든 객체에서 사용 가능
- 객체의 모든 열거 가능한 속성에 대해 반복함
- 객체의 key 값에 접근 가능하지만, value 값에 접근하는 방법은 없음
- ES6에서 추천하지 않음  

`for ( variable of object ){ 실행문; }` 
- [Symbol.iterator] 속성을 가지는 컬렉션 전용


## while()
`while ( 조건문 ) { 실행문; }`  
`do { 실행문; } while ( 조건문 )`
- 조건문이 true일 동안 실행문 반복
- while은 조건을 먼저 확인 후 true면 실행
- do...while은 먼저 실행 한 뒤 조건 확인. true면 반복


## Array.prototype.forEach()  
`Array.forEach(function (element, index, array) => { 실행문; })`
- 배열의 요소를 순회하며 모두 순회하면 실행을 멈춤  
- 오직 Array객체에서만 사용가능한 메서드였으나 ES6부터는 Map, Set 등에서도 지원됨
- break; 사용 불가  
- for문보다 속도가 빠름
- 기존 배열 값이 변경됨
- return 값이 없기 때문에 이 코드를 변수에 할당해도 undefined가 할당된다.  


## Array.prototype.map()
`Array.map(function (element, index, array) => { 실행문; })`  
- 반환값 있는 배열 반복문 매서드 (새로운 배열 생성)  
- 배열의 요소를 순회하며 모두 순회하면 실행을 멈춤
- break; 사용 불가


## Array.prototype.reduce()
`Array.reduce((accumulator, currentValue, currentIndex, array) => { /* … * / }, initialValue)`
- 가장 속도가 빠름
- 누산기(acc)는 순회 중 유지되고 반환 값은 누산기에 할당되므로 최종 결과는 하나의 값이 된다. 
- 초기값을 제공하지 않으면 배열의 첫 번째 요소를 사용하나 빈 배열에서 초기값 없이 호출하면 TypeError



