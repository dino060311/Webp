# 11장 HTML5 캔버스 그래픽 — 이론문제

---

## 1. HTML5에서 웹 페이지에 이미지, 도형 등을 그리는 그래픽 공간을 만드는 태그는?

① `<div>`  
② `<canvas>`  
③ `<graphic>`  
④ `<iframe>`

**정답: ②**

`<canvas>` 태그는 HTML5에서 웹 페이지 안에 그래픽을 그릴 수 있는 영역을 만드는 태그이다. JavaScript와 Canvas API를 이용하여 선, 도형, 이미지, 그래프 등을 그릴 수 있다.

---

## 2. HTML5 캔버스 기능에 대한 설명 중 틀린 것은?

① 캔버스는 HTML5의 표준이다.  
② 하나의 웹 페이지에 여러 개의 캔버스를 둘 수 있다.  
③ 캔버스는 2차원 그래픽만 지원하고, 3차원은 지원하지 않는다.  
④ 캔버스도 마우스 이벤트를 처리할 수 있다.

**정답: ③**

Canvas 요소는 2차원 그래픽뿐만 아니라 WebGL과 같은 그래픽 API를 통해 3차원 그래픽도 표현할 수 있으므로, 3차원은 지원하지 않는다는 설명은 틀렸다.

- 하나의 웹 페이지에 여러 개의 `<canvas>` 요소를 둘 수 있다.
- 캔버스 요소에도 마우스 이벤트를 등록하여 사용자 입력을 처리할 수 있다.

---

## 3. 다음과 같은 태그가 있을 때 주석에 맞도록 빈 라인에 자바스크립트 코드를 작성하라.

```html
<canvas id="can" width="300" height="300"></canvas>

let canvas = ______________________________; // (1) 캔버스 DOM 객체를 알아낸다.
let context = canvas.________________________; // (2) 그래픽 컨텍스트 객체를
알아낸다. context.____________________________________; // (3) 경로를 새로
구성한다. context.____________________________________; // (4) (10, 10)을
시작점으로 입력한다. context.____________________________________; // (5) (50,
50)까지 직선을 만든다. context.____________________________________; // (6)
경로에 있는 직선을 캔버스에 그린다.
```

**정답:**

```javascript
let canvas = document.getElementById("can");
let context = canvas.getContext("2d");
context.beginPath();
context.moveTo(10, 10);
context.lineTo(50, 50);
context.stroke();
```

**풀이:**

1. `document.getElementById("can")`은 id가 `can`인 캔버스 DOM 객체를 가져온다.
2. `getContext("2d")`는 2차원 그래픽 컨텍스트 객체를 가져온다.
3. `beginPath()`는 새로운 그리기 경로를 시작한다.
4. `moveTo(10, 10)`은 경로의 시작점을 `(10, 10)`으로 지정한다.
5. `lineTo(50, 50)`은 현재 위치에서 `(50, 50)`까지 직선 경로를 만든다.
6. `stroke()`는 현재 경로에 있는 직선을 캔버스에 그린다.

---

## 4. 컨텍스트 객체의 경로와 메소드에 대해 잘못 설명한 것은?

① `beginPath()`는 캔버스에 그릴 도형의 경로를 새로 시작한다.  
② `beginPath()`는 이전에 만들어진 경로를 모두 지운다.  
③ 직선, 원호, 사각형 등의 도형은 경로에 먼저 삽입된 후 캔버스에 한 번에 그려진다.  
④ `stroke()`는 경로에 있는 도형을 모두 캔버스에 그리고, 그린 도형은 경로에서 삭제한다.

**정답: ④**

`stroke()`는 현재 경로에 포함된 도형의 윤곽선을 캔버스에 그리는 메소드이다. `stroke()`를 호출해도 현재 경로가 자동으로 삭제되지는 않는다. 새로운 경로를 시작하려면 `beginPath()`를 호출해야 한다.

---

## 5. 컨텍스트 객체에서 사각형을 그리는 `rect()` 메소드와 `strokeRect()`의 차이점은 무엇인가?

**정답:**

`rect()`는 현재 경로에 사각형을 추가하는 메소드이고, `strokeRect()`는 사각형의 테두리를 캔버스에 즉시 그리는 메소드이다.

**풀이:**

1. `rect(x, y, width, height)`는 사각형을 현재 경로에 추가한다. 실제로 테두리를 표시하려면 이후에 `stroke()`를 호출해야 한다.
2. `strokeRect(x, y, width, height)`는 사각형의 테두리를 즉시 캔버스에 그리며, 현재 경로에는 사각형을 추가하지 않는다.
3. 따라서 `rect()`는 경로를 구성할 때 사용하고, `strokeRect()`는 사각형의 테두리를 바로 그릴 때 사용한다.

```javascript
// 현재 경로에 사각형을 추가한 뒤 테두리를 그린다.
context.beginPath();
context.rect(10, 10, 100, 60);
context.stroke();

// 사각형의 테두리를 즉시 그린다.
context.strokeRect(130, 10, 100, 60);
```

---

## 6. 캔버스 객체가 canvas이고 컨텍스트가 context일 때, 캔버스를 깨끗이 지우는 메소드는?

① `context.fillText(0, 0, canvas.width, canvas.height);`  
② `context.clearRect(0, 0, canvas.width, canvas.height);`  
③ `context.beginPath();`  
④ `context.closePath();`

**정답: ②**

`clearRect(x, y, width, height)`는 지정한 사각형 영역의 픽셀을 지우는 메소드이다. 캔버스의 시작 좌표 `(0, 0)`부터 전체 너비와 높이를 지정하면 캔버스 전체를 깨끗하게 지울 수 있다.

```javascript
context.clearRect(0, 0, canvas.width, canvas.height);
```

---

## 7. 다음 코드는 `lion.png` 파일의 이미지를 캔버스에 그리는 코드이다. 이 코드를 실행하면 이미지가 출력될 때도 있고, 안될 때도 있다. 이유는 무엇인가? 코드를 올바르게 수정하라.

```javascript
let img = new Image();
img.src = "lion.png";
context.drawImage(img, 10, 10);
```

**정답:**

이미지가 모두 로드되기 전에 `drawImage()`가 실행될 수 있기 때문이다. 이미지의 로드가 완료된 후 그리도록 `onload` 이벤트를 사용해야 한다.

**풀이:**

1. 이미지 파일을 불러오는 작업은 비동기적으로 진행된다.
2. `img.src`를 지정한 직후에는 이미지 로드가 끝나지 않았을 수 있다.
3. 이미지가 준비되기 전에 `drawImage()`를 호출하면 이미지가 제대로 그려지지 않을 수 있다.
4. `onload` 이벤트 안에서 `drawImage()`를 호출하면 이미지가 로드된 후 캔버스에 그릴 수 있다.

```javascript
let img = new Image();
img.onload = function () {
  context.drawImage(img, 10, 10);
};
img.src = "lion.png";
```

---

## 8. 다음 코드에 어떤 문제가 있는지 설명하라.

```javascript
let img = new Image();
img.src = "lion.png";
img.onload = function () {
  context.drawImage(img, 10, 10);
};
```

**정답:**

`img.src`를 먼저 지정한 다음 `onload` 이벤트 처리 함수를 등록하고 있다는 점이다. 이미지 로드가 시작되기 전에 이벤트 처리 함수를 먼저 등록하도록 순서를 바꾸는 것이 안전하다.

**풀이:**

1. `onload`는 이미지 로드가 완료되었을 때 실행할 함수를 등록하는 속성이다.
2. 이미지 주소를 먼저 설정하면 이미지 로드가 시작된다.
3. 이미지가 빠르게 로드되는 경우를 고려하여 로드 완료 이벤트 처리 함수를 먼저 등록하는 것이 안전하다.
4. `onload`를 먼저 지정한 다음 `src`를 설정하면 이미지가 로드된 후 `drawImage()`가 실행된다.

```javascript
let img = new Image();
img.onload = function () {
  context.drawImage(img, 10, 10);
};
img.src = "lion.png";
```
