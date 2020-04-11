# class

저번 시간에 object에 대해서 공부했다.
object는 문자열로 된 키를 사용해서 값을 저장하는 타입이다.
array처럼 한 변수에 여러 값을 저장하는 용도로 사용한다.

하지만 object 저력은 무궁무진하다.
커다란 프로그램을 짤 때 다른 모든 일과 똑같이 큰 일을 어떻게 잘 쪼개는지가 중요하다.
JavaScript를 작성하는 사람들은 object를 사용해서[^1] 큰 프로그램을 작은 object들로 나누어서 작성한다.

[^1]: 누군가는 object 대신 함수를 쓰기도 한다.

저번 시간에 만들었던 Counter 오브젝트를 다시 만들어 보자.

```js
const counter = {
    count: 0,
    countUp: function() { this.count += 1},
    printCount: function() { console.log(this.count) }
}
```

## 오늘 투표한 사람은 몇 명일까

당신이 투표소의 직원이라고 생각해보자.
당신이 할 일은 오늘 투표소에 몇 명이 들어왔는 지 세는 것이다.
요구사항은 간단하다.
당신은 투표소의 하나뿐인 문 앞에 서서, 투표소 안으로 들어가는 모든 사람의 수를 세어야 한다.

우린 이런 스마트폰 앱은 만들 수 있다.
큰 버튼이 하나 있으며, 이 버튼을 누를 때마다 count는 1이 증가한다.
다른 한 쪽에는 출력 버튼이 있으며 이 버튼을 누르면 지금까지 버튼을 몇 번 클릭했는지 알려준다.

우리는 counter object를 사용해서 이 요구사항을 완벽히 만족시킬 수 있다.

counter object하는 일은 단순하다. 똑같은 기능을 object를 사용하지 않고, count 변수만 사용해서 구현할 수 있다.
대신 비슷한 기능을 한 오브젝트에 잘 담아 놓으면 코드를 역할별로 나눌 수 있고 나중에 쉽게 필요한 코드를 수정할 수 있다.

## class의 필요성

object를 구조의 단위, 기능의 단위로 만들다 보면, 비슷한 object가 여러 필요한 상황이 있다.
할 일 관리앱의 할일을 한 오브젝트로 표현한다면, 할 일을 하나 추가할 때마다 할 일 object를 만들어야 한다.
메이플 스토리 같은 게임을 만든다면, 주황 버섯 object를 여럿 만들어야 한다.

class 문법을 사용하면 비슷한 object를 쉽게 만들 수 있다.

```javascript
class Counter {
    constructor() {
        this.count = 0;
    }

    countUp() {
        this.count += 1;
    }

    printCount() {
        console.log(this.count);
    }
}

const countA = new Counter();
countA.countUp();
countA.countUp();
countA.countUp();
countA.printCount();

const countB = new Counter();
countB.countUp();
countB.printCount();
```

위 코드는 우리가 앞서 생성했던 Counter object를 class로 다시 작성한 코드다.
class를 선언한 뒤 `new 클래스이름()` 문법을 사용해서 새로운 오브젝트를 생성한다.
`new 클래스이름()` 문법은 class 정의 안에 있는 `constructor()` 함수를 실행한다.
