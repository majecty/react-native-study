# array를 사용해 리스트 UI만들기

이 페이지는 이전 페이지에서 이어집니다.
이 페이지부터 시작하고 싶다면 이 [링크](https://snack.expo.io/@jh.majecty/0309-2-button-and-list)에서 시작해 주세요.

this.state.todo를 사용해서 리스트 UI를 만들자.

## FlatList

오늘은 리스트 뷰를 만들기 위해서 FlatList 컴포넌트를 사용할 것이다.
FlatList 컴포넌트에 대한 공식 [링크](https://snack.expo.io/@jh.majecty/0309-2-button-and-list)를 확인해보자.

## import 구문 추가

App.js 파일의 import 구문들이 모여있는 곳에 다음 코드를 추가하자.

```js
import { FlatList } from "react-native";
```

## FlatList 컴포넌트 사용하기

render함수 안에 다음 코드를 적절하게 추가하자.

```js
<FlatList
  data={this.state.todo}
  renderItem={({ item }) => <Text>{item}</Text>}
  extraData={this.state}
/>
```

## 결과 확인하기

투두를 추가할 때마다 리스트가 추가되는 것을 확인할 수 있다.
중간에 따라오지 못했다면 이 [링크](https://snack.expo.io/@jh.majecty/0309-3-array-and-list-ui)를 확인하자.
