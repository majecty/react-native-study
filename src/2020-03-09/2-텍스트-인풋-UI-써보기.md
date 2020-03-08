# 텍스트 인풋 UI 써보기

React Native Paper에는 TextInput 컴포넌트가 있다. 이 컴포넌트를 사용해보자.
시작하기 전 공식 문서의 [링크](https://callstack.github.io/react-native-paper/text-input.html)를 확인해보자.

## expo snack 기본 프로젝트를 새로 만들자

## App.js 파일 열기

## import 문 추가

import 구문들이 모여있는 곳에 다음 코드를 추가하자.

```js
import { TextInput } from "react-native-paper";
```

## State 추가

App 클래스 안에 다음 코드를 추가하자.

```js
state = {
  text: ""
};
```

## TextInput 컴포넌트를 화면에 추가

render 함수 안에 다음 코드를 추가하자.

```js
<TextInput
  label="First Text Input"
  value={this.state.text}
  onChangeText={newText => {
    console.log("You wrote " + newText);
    this.setState({
      text: newText
    });
  }}
/>
```

## 결과 확인하기

결과의 Input창에 텍스를 입력해보고, Log가 잘 찍히는지 확인하자.
