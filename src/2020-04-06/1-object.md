# object

Array는 여러 값을 한 변수에 담는 문법요소다.
Array에 있는 값들은 0부터 시작하는 숫자로 접근했다.

Object는 Array와 비슷하게 여러 값을 담는 문법 요소다.
Array와는 다른 점은 저장된 값을 접근할 때 문자열을 사용한다는 점이다.

값을 접근할 때 사용하는 문자열을 "Key"라고 말하고, Object에 저장된 값을 "Value"라고 말한다.
때로는 필드나 프로퍼티, 혹은 메소드라고 부르는 경우도 있는데,
값이 함수가 아닌 경우에는 필드나 프로퍼티라고 부르고, 값이 함수인 경우에는 메소드라고 부른다.

object변수 myObject 에 키 a로 찾은 값이 v이면,
"myObject의 a 키 값에 v가 있다.",
"myObject는 a 필드의 값이 v다.",
"myObject는 a 프로퍼티의 값이 v다.",
"myObject는 메소드 a를 가지고 있다."로 표현한다.

## Object 예시

```js
const mahjongScore = {
    "리치": 1,
    "일발": 1,
    "핑후": 1,
    "치또이": 2,
    "일기통관": 2
    threeClosedTriplets: 2
}

console.log(mahjongScore);

mahjongScore["또이또이"] = 2
console.log(mahjongScore["또이또이"]);

console.log(mahjongScore.threeClosedTriplets);
console.log("삼암각은 " + mahjongScore.threeClosedTriplets + "판짜리 역이다");

console.log(mahjongScore);
```


## Object 생성하기

Object는 중괄호(`{}`)를 사용해서 생성한다.

```js
const emptyObject = {};
console.log(emptyObject);
```

Object를 생성할 때 값을 같이 넣어줄 수 있다.

```js
const smallObject = {
    a: 3,
    b: "z"
};

console.log(smallObject);
```

## Object의 값 읽기

Object의 값은 `(object 변수 이름).(필드 이름)`이나 `(object 변수 이름)["필드 이름"]`으로 접근한다.

```js
const smallObject2 = {
    a: 2,
    b: 3.14
};

console.log(smallObject2.a);
console.log(smallObject2["a"]);
```

## Object에 값 쓰기

Object에 값을 쓸 때는 `(object 변수 이름).(필드 이름) = (새로운 값)`을 쓰거나 `(object 변수 이름)[("필드 이름")] = (새로운 값)`을 쓴다.

```js
const smallObject3 = {
    a: 3,
    b: "xxx"
};

smallObject3.a = "yyy";
smallObject3.b = 8;

console.log(smallObject3);
```

## Object에서 키 값 지우기

Object에 쓰인 값을 지우고 싶을 때는 `delete (object 변수 이름).(필드 이름)`나 `delete (object 변수 이름)["(필드 이름)"]`을 사용한다.

```js
const smallObject4 = {
    a: 3,
    b: 9
}

console.log(smallObject4);

delete smallObject4.a;
console.log(smallObject4);

delete smallObject4["b"]
console.log(smallObject4);

```

## 언제 `.` 문법을 쓰고 언제 `[""]` 문법을 쓸까

`.` 문법과 `[""]` 문법은 거의 똑같은 일을 할 수 있지만 받아들일 수 있는 키의 형태가 조금 다르다.
`.` 문법으로 쓸 수 있는 키는 변수 이름이나 함수 이름과 같은 제약을 받는다.
알파벳이나 '_', '$' 로 시작해야 한다. `[""]` 문법에서는 그러한 제약이 없다.

```js
const smallObject4 = {
    a: 7,
    "333": 8
}

console.log(smallObject4);
```

`[""]` 문법보다는 `.`문법을 더 자주 사용한다.

## console.log도?

우리는 이미 `.` 문법을 많이 사용하고 있다.
대표적인 코드가 `console.log`다. console은 object이며 log 메소드를 가지고 있다.
자바스크립트에서 `.`을 본다면 전부 Object라고 이해할 수 있다.

다음은 숫자를 세주는 counter object다. object에 메소드로 있는 함수는 `this` 키워드를 사용해서 object의 다른 필드나 메소드를 사용할 수 있다.

```js
const counter = {
    value: 0,
    countUp: function () {
        this.value += 1;
    },
    print: function () {
        console.log(this.value);
    }
};

counter.print();

counter.countUp();
counter.print();

counter.countUp();
counter.countUp();
counter.print();

counter.value = -10;
counter.print();
```
