# for 문

JavaScript언어는 반복을 위한 문법으로 for문과 while문을 제공한다.

## for문의 구조

for문은 하는 일에 비하여 복잡한 문법을 가지고 있다.
각 문법 구조가 하는 일을 이해한 뒤 자주 쓰이는 패턴을 외우자.

아래는 for문의 예시다.

```javascript
for (
  let iterationCount = 0;
  iterationCount < 2;
  iterationCount = iterationCount + 1
) {
  console.log(iterationCount);
}
```

for문은 3가지 요소로 이루어져 있다. `for` 키워드, `()`로 둘러쌓인 3가지 식.
`{}`로 둘러쌓인 반복하는 코드.
그 중 `()`로 둘러쌓인 3가지 식이 복잡하니 뒤에서 다시 설명하겠다.

## for문 풀어보기

for문을 동작을 이해하기 위해서는 반복되는 코드를 직접 풀어써 서보면 도움이 된다.
위의 예시 코드와 똑같은 동작을 하는 코드를 for문 없이 만들어보자.

아래는 for문의 동작을 풀어 쓴 예시다.

```javascript
let iterationCount = 0;
if (iterationCount < 2) {
  console.log(iterationCount);
  iterationCount = iterationCount + 1;

  if (iterationCount < 2) {
      console.log(iterationCount);
      iterationCount = iterationCount + 1;

      if (iterationCount < 2) {
          console.log(iterationCount);
          iterationCount = iterationCount + 1;
          ...
      }
  }
}
```

위 예시의 코드를 한 줄 한 줄 풀어서 이해해보자.

### 1 번째 줄

```javascript
let iterationCount = 0;
```

시작은 변수의 선언이다. 이 변수는 두 가지 용도로 사용된다.
하나는 지금까지 반복을 몇 번 했는지 표시하는 용도다.
다른 하나는 종료 조건을 확인하기 위한 용도다.
다른 코드를 더 읽으며 사용 예를 확인하자.

### 2 번째 줄

```javascript
if (iterationCount < 2) {
```

변수를 선언한 뒤 바로 종료 조건을 확인한다.
예시의 for문은 `iterationCount < 2` 이면 반복한다.
`iterationCount >= 2`가 되었을 때 반복을 끝낸다.
아직 `iterationCount`의 값이 0이므로 if문 안에 진입한다.

### 3 번째 줄

```javascript
console.log(iterationCount);
```

3 번째 줄은 우리가 반복할 코드다.
이 코드의 동작은 iterationCount를 출력하는 것이다.

### 4 번째 줄

```javascript
iterationCount = iterationCount + 1;
```

4 번째 줄은 iterationCount 값을 하나 증가시킨다.
iterationCount 값은 이전에 0이었고, 이 줄을 실행 후에 1이 된다.

### 6 번째 줄

5 번째 줄은 비어있어서 바로 6 번째 줄이다.

```javascript
if (iterationCount < 2) {
```

이 줄부터는 2 번째의 반복이다. iterationCount의 값이 1이므로 if문 안의
블록을 실행한다.

### 7 번째 줄

```javascript
console.log(iterationCount);
```

iterationCount값이 1이므로 1을 출력한다.

### 8 번째 줄

```javascript
iterationCount = iterationCount + 1;
```

반복을 한 번 더 했으므로 iterationCount값을 하나 증가시킨다.
8 번째 줄을 시작하기 전의 iterationCount의 값은 1이다.
8 번째 줄을 시작한 후의 iterationCount의 값은 2이다.

### 10 번째 줄

9 번째 줄은 빈 줄이므로 생략한다.

```javascript
if (iterationCount < 2) {
```

iterationCount의 값이 2이기 때문에 if문의 조건이 만족되지 않아
if문의 block을 실행하지 않는다.

## for 문의 세 요소 일반화

방금 풀어본 식을 일반화 해서 다시 확인하자.
for 문 안의 4가지 요소를 각각 INITIALIZE_EXPRESSION, CONDITION, FINAL_EXPRESSION, STATEMENT
라고 부르자.[^mdn에서-가져온-용어]

[^mdn에서-가져온-용어]: [MDN의 for문 설명](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Statements/for)에서 가져온 용어다.

```javascript
for (INITIALIZE_EXPRESSION; CONDITION; FINAL_EXPRESSION) {
  STATEMENT;
}
```

이 for문을 풀면 다음과 같다.

```javascript
INITIALIZE_EXPRESSION;
if (CONDITION) {
  STATEMENT;
  FINAL_EXPRESSION;

  if (CONDITION) {
      STATEMENT;
      FINAL_EXPRESSION;

      if (CONDITION) {
          STATEMENT;
          FINAL_EXPRESSION;
          ...
      }
  }
}
```

위 관계를 이해했다면 for문에 대한 모든 것을 끝냈다.
