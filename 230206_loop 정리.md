for() vs. while() vs. forEach() vs. map()  

### for()  
for ( 초기화식; 조건식; 증감식 ){ 실행문; }  
for ( property in object ){ 실행문; }  
for ( variable of object ){ 실행문; } 
- 조건식이 true일 동안 순회  
- 멈추고 싶다면 break; 사용  

### while()
while ( 조건문 ) { 실행문; }  
do { 실행문; } while ( 조건문 )
- 조건문이 true일 동안 실행문 반복
- while은 조건을 먼저 확인 후 true면 실행
- do...while은 먼저 실행 한 뒤 조건 확인. true면 반복

### Array.prototype.forEach()  
배열명.forEach(function(매개변수) { 실행문; })
- 배열의 요소를 순회하며 모두 순회하면 실행을 멈춤  
- break; 사용 불가  
- for문보다 속도가 빠름
- 기존 배열의 값이 바뀜

### Array.prototype.map()
배열명.map(function(매개변수) { 실행문; })  
- 반환값 있는 배열 반복문 매서드 (새로운 배열 생성)  
- 배열의 요소를 순회하며 모두 순회하면 실행을 멈춤
- break; 사용 불가

