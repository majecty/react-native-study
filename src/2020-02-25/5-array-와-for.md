# Array와 for문

Array와 for문은 함께 자주 쓰인다.
Array의 모든 값에 대해서 동작하는 코드를 짤 때 for문을 사용해야 하기 때문이다.

## Array의 모든 값 출력하기

4가지 과일의 이름을 담은 array를 선언한 뒤 이 array가 담고 있는 모든 값을 출력해보자.

```javascript
let fruits = ["avocado", "banana", "cherries", "durian"];
```

아래와 같이 출력하는 코드를 짤 수 있다.

```javascript
console.log(fruits[0]);
console.log(fruits[1]);
console.log(fruits[2]);
console.log(fruits[3]);
```

for문을 써서 똑같은 일을 하는 코드를 만들어보자.

```javascript
for (let i = 0; i < myArray.length; i = i + 1) {
  console.log(fruits[i]);
}
```

아래 코드는 array의 모든 내용을 출력한다.

```javascript
let myArray = ["avocado", "banana", "cherries", "durian"];
for (let i = 0; i < myArray.length; i = i + 1) {
  console.log(myArray[i]);
}
```
