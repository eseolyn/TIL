20220405 tue  
Nomad Coders  
Movie web service  
  
오늘 할 일  
#3.6~3.8 converter  
___
recap  
1. state 생성  
2. input의 value를 state로 연결 - 어디서든 input의 value를 수정 가능  
3. onChange함수 생성 - (input에서 리스닝하는)데이터를 업데이트 해줌  
input에 뭔가를 써 넣을때, onChange함수가 실행, target value(input value)를 얻게됨, 데이터가 변경되면 input이 따라 업데이트됨  
input value를 연결시키는 이유 - input값을 외부에서도 수정하기 위해(예:레셋버튼)  
___
hour 데이터 연결  
reset버튼 만들기  

flip버튼 만들기  
flip state & onFlip함수 만들기 : 현재state를 바탕으로 새로운 state를 계산해냄:  
const onFlip = () => setFlipped((currnet) => !current);  
input에 명제 주기:  
disabled={flipped}  
  
hours input  
hours input value 얻기(minutes 참고ㅎㅎ)  
flip상태에서만 계산된 값 나오게 변경 - 삼항연산자(if문을 인라인 형태로 작성)  
Flip시 입력값 reset하기  
```
function MinutesToHours() {
      const [amount, setAmount] = React.useState(0);
      const [inverted, setInverted] = React.useState(false);
      const onChange = (event) => {
        setAmount(event.target.value);
      };
      const reset = () => setAmount(0);
      const onFlip = () => {
        setInverted((current) => !current);
        reset();
      };
      return (
        <div>
          <div>
            <label htmlFor="minutes">Minutes</label>
            <input
              value={inverted ? amount * 60 : amount}
              id="minutes"
              placeholder="Minutes"
              type="number"
              onChange={onChange}
              disabled={inverted}
            />
          </div>
          <div>
            <label htmlFor="hours">Hours</label>
            <input
              value={inverted ? amount : Math.round(amount / 60)}
              id="hours"
              placeholder="Hours"
              type="number"
              disabled={!inverted}
              onChange={onChange}
            />
          </div>
          <button onClick={reset}>Reset</button>
          <button onClick={onFlip}>Invert</button>
        </div>
      );
    }
```
___
내일 할 일  
#3.9 code challenge - converter 완성하기
