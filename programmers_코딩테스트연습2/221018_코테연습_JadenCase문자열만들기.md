20221018 Tue  
프로그래머스  
코딩테스트문제 Level.2

JadenCase 문자열 만들기
---
문제 설명  
JadenCase란 모든 단어의 첫 문자가 대문자이고, 그 외의 알파벳은 소문자인 문자열입니다.  
단, 첫 문자가 알파벳이 아닐 때에는 이어지는 알파벳은 소문자로 쓰면 됩니다. (첫 번째 입출력 예 참고)  
문자열 s가 주어졌을 때, s를 JadenCase로 바꾼 문자열을 리턴하는 함수, solution을 완성해주세요.  

제한 조건  
- s는 길이 1 이상 200 이하인 문자열입니다.  
- s는 알파벳과 숫자, 공백문자(" ")로 이루어져 있습니다.  
  - 숫자는 단어의 첫 문자로만 나옵니다.  
  - 숫자로만 이루어진 단어는 없습니다.  
  - 공백문자가 연속해서 나올 수 있습니다.  

---
나의 풀이
```jsx
function solution(s) {
    var answer = '';
    const arr = s.split(' ');
    for(let i=0; i<arr.length; i++){
        arr[i] = arr[i].charAt(0).toUpperCase() + arr[i].slice(1).toLowerCase();
    }
    return answer = arr.join(' ');
}
```
toUpperCase()는 문자열 전체를 바꾸므로  
첫번째 문자만 바꾸기위해선 slice한 뒤 변환하고 다시 join해야 한다.  
나머지 문자열을 toLowerCase를 하지 않았다 테스트케이스 실패로 뜨길래 추가했다.
꽤 단순했던 문제

---
다른 사람의 풀이
```jsx
function solution(s) {
    return s.split(" ").map(v => v.charAt(0).toUpperCase() + v.substring(1).toLowerCase()).join(" ");
}
```
대체로 비슷한 풀이가 많았다.  
map과 substring을 사용  
loop와 문자열 자르는 방법은 다양해서 활용가능한 다른 method들도 더 있을것같다.




