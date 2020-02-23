# Array

JavaScript의 Array와 반복은 서로를 잘 알면 서로를 이해하기 좋다.
For문을 더 공부하기 전에 Array를 공부하자.

## Array의 필요성

지금까지는 값 하나당 한 변수에 담았다.
10개의 값이 필요하면 10개의 변수를 선언했다.

프로그램을 짜다 보면, 1,000개, 10,000개 이상의 값도 다루어야 한다.
갤럭시 S20이 찍은 사진이 1억 화소를 가지고 있다면,
갤럭시가 찍은 사진을 편집하는 프로그램은 1억개 이상의 값을 다룰 수 있어야 한다.

프로그래밍 언어는 컬렉션이라는 타입을 도입해 이 문제를 해결한다.
컬렉션 타입의 값은 수 많은 다른 값을 가진다.

## Array 예시

Array는 컬렉션 타입중 가장 간단한 타입이다.
수많은 값들을 포함할 수 있으며 각 값에 숫자를 하나씩 지정해서 접근한다.

```javascript
const myArray = [1, 2, 3];
console.log(myArray[0]);
console.log(myArray[1]);
console.log(myArray[2]);
```

위의 코드는 값을 3개 가지는 array를 선언하고 하나씩 출력하는 코드다.
주의해야할 점은 array에 있는 모든 값은 0번부터 시작한다는 점이다.
array에 값이 3개 있다면 `array[0]`, `array[1]`, `array[2]` 표현을 통해
세 값에 접근할 수 있다.
array에 값이 5개 있다면 `arra[0]`, `array[1]`, `array[2]`, `array[3]`, `array[4]` 표현을 통해
다섯 값에 접근할 수 있다.

## Array 값 만들기

`[]` 안에 값을 넣어서 Array값을 만들 수 있다.

```javascript
const emptyArray = [];
const oneElementArray = ["Egg"];
const manyElementArray = ["Egg", 4, 1, 2, "Book"];
```

## Array 값 접근하기

Array 변수 뒤에 `[number]`를 붙여서 Array 값 안에 있는 값에 접근할 수 있다.

```javascript
const myArray = [1, 2, 3];
console.log(myArray[1]);
myArray[1] = 7;
console.log(myArray[1]);
```

## Array 에 총 몇 개의 값이 들어있는 지 확인하기

Array 변수에 `.length`를 붙여서 array가 몇 개의 값을
가지고 있는지 확인할 수 있다.

```javascript
const myArray = [1, 2, 3];
console.log(myArray.length);

const otherArray = [];
console.log(otherArray.length);
```

## Array에 맨 뒤에 값을 추가하고 빼기

Array 타입의 변수에 `.push`를 붙여서 맨 뒤에 원하는 값을 하나 추가할 수 있다.
`myArray.push("mushroom")`는 `myArray`에 `"mushrrom"`이 추가한다.
`myArray.push("mushroom")`의 값은 `myArray.length`가 된다.

Array 타입의 변수에 `.pop`을 붙여서 맨 뒤에서 값 하나를 없앨 수 있다.
`myArray.pop()`는 `myArray`의 맨 마지막 원소를 하나 뺀다.
`myArray.pop()`의 값은 맨 마지막에서 빠진 원소다.

[MDN의 push 문서](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/push)에
더 자세한 설명이 있다.

```javascript
const myArray = ["banana", "tomato", "avocado", "eggplant"];
console.log(myArray);
console.log(myArray.push("mushroom"));
console.log(myArray);
console.log(myArray.pop());
console.log(myArray);
```

## Array의 맨 앞에서 값을 추가하고 빼기

```javascript
const myArray = ["black", "white", "blue", "red"];
console.log(myArray);
console.log(myArray.unshift("green"));
console.log(myArray);
console.log(myArray.shift());
console.log(myArray);
```

## Array의 중간에 값을 넣거나 빼기

Array 타입의 값에 n번째 위치에 새로운 값을 추가하고 싶다면 `myArray.splice(n, 0, newValue)` 표현을 사용하자.

```javascript
const myArray = ["elephant", "cat"];
myArray.splice(1, 0, "dog");
console.log(myArray);
```

Array 타입의 값에서 n번째 위치의 값을 삭제하고 싶다면 `myArray.splice(n, 1)` 표현을 사용하자.

```javascript
const myArray = ["Agatha Christie", "Arthur Conan Doyle", "Dorothy L. Sayers"];
console.log(myArray.splice(1, 1));
console.log(myArray);
```
