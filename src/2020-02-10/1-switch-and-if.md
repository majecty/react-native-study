# 스위치 컴포넌트와 if문

전에 실습했던 스위치 예시에 if문을 사용해서 새로운 기능을 추가해보자.
지난주에 실습한 환경을 찾지 못했다면 이 [링크](https://snack.expo.io/@jh.majecty/0127)의 프로젝트에서
다시 시작하자.

아래 동영상을 보면, 스위치를 클릭할 때마다 번갈아 가면서 "Switch is on"과 "Switch is off"가 출력된다.
if문을 사용해서 이 동작과 똑같은 동작을 만들어보자.

![switch를 조작하면 텍스트가 바뀜](./1-switch-print.apng)

## 코드 수정하기

코드를 수정하면서 헷갈리는 곳은 이 [링크](https://snack.expo.io/@jh.majecty/0210-switchif)의
코드를 보면서 확인하자. 우리는 "components/Switches.js" 파일만을 수정한다.

`const isSwitchOn = this.state.isSwitchOn` 다음 줄에 message 변수를 선언하자.
if문을 사용해서 isSwitchOn의 변수가 true 값이면 message에 `"Switch is on"`을 대입하자.
isSwitchOn의 변수가 false 값이면 message에 `"Switch is off"`값을 대입하자.

```js
render() {
  const isSwitchOn = this.state.isSwitchOn;
  let message = "";
  if (isSwitchOn) {
    message = "Switch is on";
  } else {
    message = "Switch is off";
  }
  return (
```

Switch 아래에 Paragraph를 만들어서 message 변수의 값을 출력하자.

```js
<View style={styles.row}>
  <Paragraph> Toggle </Paragraph>
  <Switch
    value={isSwitchOn}
    onValueChange={() => {
      console.log(isSwitchOn);
      this.setState({ isSwitchOn: !isSwitchOn });
    }}
  />
</View>
<Paragraph>{message}</Paragraph>
```

## 결과 확인하기

핸드폰에서 결과를 직접 확인해보자.
