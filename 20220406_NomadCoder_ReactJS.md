20220406 wed  
Nomad Coders  
Movie web service  
  
오늘 할 일  
#3.9 code challenge - converter 완성하기  
1. App() selecter 만들기  
2. KmToMiles() 완성하기  
3. ~css 곁들여보기~  
___
코딩 흐름 순서  
## App컴포넌트  
목표: 셀렉트로 유닛을 선택해 선택한 유닛만 화면에 뜨도록 함  
1. 셀렉트: 옵션으로 인덱스 주기  
2. 인덱스값 state만들기  
3. 인덱스값 따라 나타낼 컴포넌트 if문으로 정하기  
  
## KmToMiles컴포넌트  
목표: (MinutesToHours복습)input value 리스닝& 입력, invert적용  
1. 인풋과 라벨만들고 연결  
2. value 얻어낼 state와 onChange, input에 value 주기  
3. 리셋버튼  
4. flip버튼  
5. flip상태 리스닝할 state와 onflip, input에 disabled 설정  
  
느낀점: 목표와 전체적인 흐름을 알아야 코딩을 쓸 때 막힘이 덜 하다.  
처음부터 뭘 해야할지 모를때의 자괴감은...끔찍해ㅠ 많이 하다보면 좀 나아질까?  
___

#6 복습  
useEffect: 컴포넌트가 처음 render될 때, 또는 특정부분이 변할 때만 실행되는 코드 작성법  
