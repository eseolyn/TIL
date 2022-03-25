20220323 wed
nomadcoder
ReactJS Movie Web Service
#5.0 ~ 5.1 : create React App

어제부터 다시 깃헙 시작
근데 자꾸만 permission denied가 떠서 연결할 수 가 없었다.
나는 니꼬쌤이 시작하라던 위치에 파일을 만들어서 했을 뿐인데...
결국 바탕화면으로 옮기고 나서야 깃헙에 연결할 수 있었다.
그러던 중 니꼬쌤의 '개발자를 위한 윈도우 셋업'강의 발견
고생한 김에 셋업 다 해버리자는 생각으로 시작했다가 또 스트레스 받았다ㅋㅋ 뭐가 이렇게 걸리는게 많은거야...
하루종일 셋업 한 뒤 다시 ReactJS 강의 #5로 돌아옴

node.JS, npm, npx 순으로 설치
npx create-react-app {원하는 파일명}
와우! react에서 알아서 기본 app을 만들어줬습니다~
이제 내것으로 만들기 위해 뼈대가 될 것만 남기고 싹 다 삭제

index.js
```
import React from "react";
import ReactDOM from "react-dom";
import App from "./App";

ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById("root")
);
```

App.js
```
import Button from "./Button";
import styles from "./App.module.css";

function App() {
  return (
    <div>
      <h1 className={styles.title}>Welcome back!</h1>
      <Button text={"Continue"} />
    </div>
  );
}

export default App;
```

Button.js
```import PropTypes from "prop-types";
import styles from "./Button.module.css";

function Button({ text }) {
  return <button className={styles.btn}>{text}</button>;
}

Button.propTypes = {
  text: PropTypes.string.isRequired,
};

export default Button;
```
타이틀과 버튼에 직접 css를 쓰고싶지 않다.
그렇다고 css파일을 쓰고싶지도 않다.
이것들은 내 모든 페이지의 모든 버튼을 똑같이 만들어버릴테니까
그럴때 module.css를 만들어 import하면 페이지에서 style에 랜덤으로 이름을 붙여 style을 분할해 적용할 수 있다.
module에 쓴 css를 타이틀과 버튼에 className으로 연결

App.module.css
```
.title {
  font-family: sans-serif;
  font-size: 18px;
}
```
Button.module.css
```
.btn {
  color: white;
  background-color: tomato;
}
```
css와 비슷...

터미널에 npm start 실행 후 개발자툴을 켜 확인해보면 타이틀과 버튼에 붙은 css에 랜덤한 이름이 붙어있다. 성공!

다음섹션에선 state와 props에 이어 중요한 Effect를 배우게 될 것!

TIL이 이렇게 쓰는게 맞나...?
