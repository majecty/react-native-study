# p5.js

## 프로세싱

프로세싱은 인터렉티브 아트를 만들기 위한 개발 환경이다. 2001년 MIT 미디어 랩의
Casey Reas와 Ben Fry가 시작한 프로젝트다. 쉽게 화면에 그래픽 요소를 표시할 수 있
다. 직관적으로 화면의 픽셀들을 다룰 수 있고, 예시 문서들이 풍부한 것이 장점이다.

## p5.js

프로세싱과 같은 API를 JavaScript에서도 할 수 있게 만든 프로젝트다. 프로세싱에 대
한 장점으로 웹에서 바로 실행할 수 있다.

## p5.js 가입하기

[https://editor.p5js.org](https://editor.p5js.org)에 접속해서 회원가입을 하자.

## p5.js editor 사용하기

p5.js 웹사이트는 브라우저에서 실행하는 개발환경을 제공한다.
[https://editor.p5js.org](https://editor.p5js.org)에 들어가면 왼쪽에 코드를 작성
할 수 있는 창이, 오른쪽에 결과를 보는 창이 있다.

## Hello World

다음 코드는 400 x 400 픽셀의 화면에 0~255사이 중 220 을 의미하는 회색을 칠하는코
드다.

```js
function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(220);
}
```

## Showcase 보기

p5.js의 Showcase 메뉴에 p5.js로 작성한 몇가지 프로젝트들이 소개되어 있다.
[https://p5js.org/showcase/](https://p5js.org/showcase/)

## Example

p5.js의 Example 페이지는 p5.js로 할 수 있는 다양한 작업들이 친절하게 설명되어 있
다. (https://p5js.org/examples/)[https://p5js.org/examples/]

## setup과 draw

아래 코드는 p5js.org의 예시 페이지에서 가져왔다. setup은 프로그램이 시작할 때 딱
한 번 호출된다. draw는 매 프레임[^1]마다 호출되어 해당 프레임에 보여주어야할 화
면을 만든다.

[^1]:
  컴퓨터의 모니터는 1초 안에 화면을 수십번 다시 그린다. 이때 그려지는 한 화면을
  프레임이라고 부른다. 초당 60번 다시 그리면 1초에 60프레임을 그린다고 말한다.

```js
let y = 100;

// The statements in the setup() function
// execute once when the program begins
function setup() {
  // createCanvas must be the first statement
  createCanvas(720, 400);
  stroke(255); // Set line drawing color to white
  frameRate(30);
}
// The statements in draw() are executed until the
// program is stopped. Each statement is executed in
// sequence and after the last line is read, the first
// line is executed again.
function draw() {
  background(0); // Set the background to black
  y = y - 1;
  if (y < 0) {
    y = height;
  }
  line(0, y, width, y);
}
```

## 세모, 네모, 타원, 동그라미 그리기

아래 코드는 p5js의 예시에서 가져왔다. 시간에 따라 변화가 없는 프로그램은
`setup`함수만으로 만들 수 있다.

```js
function setup() {
  // Sets the screen to be 720 pixels wide and 400 pixels high
  createCanvas(720, 400);
  background(0);
  noStroke();

  fill(204);
  triangle(18, 18, 18, 360, 81, 360);

  fill(102);
  rect(81, 81, 63, 63);

  fill(204);
  quad(189, 18, 216, 18, 216, 360, 144, 360);

  fill(255);
  ellipse(252, 144, 72, 72);

  fill(204);
  triangle(288, 18, 351, 360, 288, 360);

  fill(255);
  arc(479, 300, 280, 280, PI, TWO_PI);
}
```

## 마우스 입력

아래 코드는 p5js의 예시에서 가져왔다. 마우스 좌표를 `mouseX`, `mouseY`라는 변수
로부터 읽을 수 있다. 개인적으로 마우스 좌표를 읽을 수 있는 가장 간단한 방법이라
고 생각한다.

```js
function setup() {
  createCanvas(720, 400);
  noStroke();
  rectMode(CENTER);
}

function draw() {
  background(230);
  fill(244, 122, 158);
  rect(mouseX, height / 2, mouseY / 2 + 10, mouseY / 2 + 10);
  fill(237, 34, 93);
  let inverseX = width - mouseX;
  let inverseY = height - mouseY;
  rect(inverseX, height / 2, inverseY / 2 + 10, inverseY / 2 + 10);
}
```
