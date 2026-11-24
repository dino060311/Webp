# 11장 HTML5 캔버스 그래픽 — 실습문제

---

## 1. 다음 HTML 페이지와 출력 결과를 참고하여 원을 그리는 drawCircle() 함수를 작성하라.

**정답:**

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>drawCircle() 만들기</title>
    <script>
      function drawCircle(ctx, x, y, radius) {
        ctx.beginPath();
        ctx.arc(x, y, radius, 0, 2 * Math.PI);
        ctx.stroke();
      }
    </script>
  </head>
  <body>
    <h3>drawCircle() 만들기</h3>
    <hr />
    <canvas
      id="myCanvas"
      width="300"
      height="220"
      style="background-color:aliceblue"
    ></canvas>
    <script>
      let canvas = document.getElementById("myCanvas");
      let context = canvas.getContext("2d");

      drawCircle(context, 100, 100, 80);
      drawCircle(context, 150, 150, 30);
    </script>
  </body>
</html>
```

1. `drawCircle(ctx, x, y, radius)` 함수는 그래픽 컨텍스트 객체 `ctx`, 원의 중심 좌표 `(x, y)`, 반지름 `radius`를 매개변수로 받는다.
2. `beginPath()`로 새로운 경로를 시작한다.
3. `arc()` 메소드에 중심 좌표, 반지름, 시작 각도 `0`, 끝 각도 `2 * Math.PI`를 지정하면 한 바퀴 전체의 원이 만들어진다.
4. `stroke()`는 경로에 있는 원의 테두리를 캔버스에 그린다.
5. 예시에서는 중심이 `(100, 100)`이고 반지름이 `80`인 원과 중심이 `(150, 150)`이고 반지름이 `30`인 원을 그린다.

---

## 2. 다음 HTML 페이지와 출력 결과를 참고하여 다각형을 그리는 drawPolygon()을 작성하라.

**정답:**

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>drawPolygon() 만들기</title>
    <script>
      function drawPolygon(ctx, xArray, yArray) {
        if (xArray.length === 0 || xArray.length !== yArray.length) {
          return;
        }

        ctx.beginPath();
        ctx.moveTo(xArray[0], yArray[0]);

        for (let i = 1; i < xArray.length; i++) {
          ctx.lineTo(xArray[i], yArray[i]);
        }

        ctx.closePath();
        ctx.stroke();
      }
    </script>
  </head>
  <body>
    <h3>drawPolygon() 만들기</h3>
    <hr />
    <canvas
      id="myCanvas"
      width="220"
      height="220"
      style="background-color:aliceblue"
    ></canvas>
    <script>
      let canvas = document.getElementById("myCanvas");
      let context = canvas.getContext("2d");

      let xs = [100, 10, 150, 210];
      let ys = [10, 100, 200, 60];

      drawPolygon(context, xs, ys);
    </script>
  </body>
</html>
```

1. `drawPolygon(ctx, xArray, yArray)` 함수는 다각형의 x 좌표 배열과 y 좌표 배열을 매개변수로 받는다.
2. 두 배열의 첫 번째 원소를 `moveTo()`로 지정하여 다각형의 시작점으로 이동한다.
3. 반복문에서 나머지 좌표를 `lineTo()`로 연결한다.
4. `closePath()`는 마지막 점과 첫 번째 점을 연결하여 다각형의 경로를 닫는다.
5. `stroke()`로 다각형의 테두리를 캔버스에 그린다.

예시의 좌표는 `(100, 10)`, `(10, 100)`, `(150, 200)`, `(210, 60)`이며, 이 네 점을 순서대로 연결하여 사각형 모양의 다각형을 만든다.

---

## 3. 올림픽 오륜기를 캔버스에 출력하는 웹 페이지를 작성하라.

**정답:**

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>오륜기 그리기</title>
    <script>
      function drawRing(ctx, x, y, color) {
        ctx.beginPath();
        ctx.strokeStyle = color;
        ctx.lineWidth = 4;
        ctx.arc(x, y, 30, 0, 2 * Math.PI);
        ctx.stroke();
      }

      function drawOlympicRings(ctx) {
        // 위쪽 세 개의 고리
        drawRing(ctx, 60, 60, "blue");
        drawRing(ctx, 130, 60, "black");
        drawRing(ctx, 200, 60, "red");

        // 아래쪽 두 개의 고리
        drawRing(ctx, 95, 95, "yellow");
        drawRing(ctx, 165, 95, "green");
      }
    </script>
  </head>
  <body>
    <h3>오륜기 그리기</h3>
    <hr />
    <canvas
      id="myCanvas"
      width="300"
      height="160"
      style="background-color:aliceblue"
    ></canvas>
    <script>
      let canvas = document.getElementById("myCanvas");
      let context = canvas.getContext("2d");
      drawOlympicRings(context);
    </script>
  </body>
</html>
```

1. `drawRing()` 함수는 원의 중심 좌표와 선 색을 매개변수로 받아 하나의 고리를 그린다.
2. `arc()`에 시작 각도 `0`, 끝 각도 `2 * Math.PI`를 지정하여 원을 만든다.
3. `strokeStyle`로 고리의 색을 지정하고 `lineWidth`로 선의 굵기를 지정한다.
4. `drawOlympicRings()` 함수에서 파랑, 검정, 빨강 고리를 위쪽에 배치하고 노랑, 초록 고리를 아래쪽에 배치한다.
5. 각 고리는 `stroke()`로 테두리만 그리므로 내부는 채워지지 않는다.

---

## 4. 캔버스를 이용하여 자신의 사진 위에 자신의 이름을 출력하는 웹 페이지를 작성하라.

### (1) 사진 위에 자신의 이름을 출력하라.

**정답:**

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>사진과 이름 출력 (1)</title>
  </head>
  <body>
    <h3>사진과 이름 출력</h3>
    <hr />

    <p>사진 선택: <input type="file" id="photoFile" accept="image/*" /></p>
    <p>
      이름 입력: <input type="text" id="userName" value="내 이름" />
      <button type="button" onclick="drawPhotoAndName()">출력</button>
    </p>

    <canvas
      id="myCanvas"
      width="300"
      height="220"
      style="background-color:aliceblue"
    ></canvas>

    <script>
      let canvas = document.getElementById("myCanvas");
      let context = canvas.getContext("2d");
      let photo = new Image();
      let photoLoaded = false;

      document
        .getElementById("photoFile")
        .addEventListener("change", function () {
          let file = this.files[0];
          if (!file) return;

          let imageURL = URL.createObjectURL(file);
          photo.onload = function () {
            photoLoaded = true;
            drawPhotoAndName();
            URL.revokeObjectURL(imageURL);
          };
          photo.onerror = function () {
            alert("이미지를 불러오지 못했습니다.");
            URL.revokeObjectURL(imageURL);
          };
          photo.src = imageURL;
        });

      function drawPhotoAndName() {
        if (!photoLoaded) {
          alert("먼저 사진 파일을 선택하세요.");
          return;
        }

        let name = document.getElementById("userName").value;
        context.clearRect(0, 0, canvas.width, canvas.height);

        // 사진을 캔버스 크기에 맞추어 그린다.
        let scale = Math.min(
          canvas.width / photo.width,
          canvas.height / photo.height,
        );
        let w = photo.width * scale;
        let h = photo.height * scale;
        let x = (canvas.width - w) / 2;
        let y = (canvas.height - h) / 2;
        context.drawImage(photo, x, y, w, h);

        // 사진 위에 이름을 채워서 출력한다.
        context.font = "italic bold 34px Georgia";
        context.textAlign = "center";
        context.textBaseline = "middle";
        context.fillStyle = "purple";
        context.fillText(name, canvas.width / 2, canvas.height - 30);
      }
    </script>
  </body>
</html>
```

사진 파일을 선택하면 `Image` 객체에 사진을 불러오고, 사진이 모두 로드된 후 `drawPhotoAndName()`을 실행한다. `drawImage()`로 사진을 캔버스에 출력한 다음 `fillText()`로 이름을 사진 위에 표시한다. `fillStyle`은 글자 색을 지정하고, `textAlign`과 `textBaseline`은 글자의 기준 위치를 정한다.

### (2) 사진 위에 테두리가 있는 자신의 이름을 출력하라.

**정답:**

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>사진과 이름 출력 (2)</title>
  </head>
  <body>
    <h3>사진과 이름 출력</h3>
    <hr />

    <p>사진 선택: <input type="file" id="photoFile" accept="image/*" /></p>
    <p>
      이름 입력: <input type="text" id="userName" value="내 이름" />
      <button type="button" onclick="drawPhotoAndName()">출력</button>
    </p>

    <canvas
      id="myCanvas"
      width="300"
      height="220"
      style="background-color:aliceblue"
    ></canvas>

    <script>
      let canvas = document.getElementById("myCanvas");
      let context = canvas.getContext("2d");
      let photo = new Image();
      let photoLoaded = false;

      document
        .getElementById("photoFile")
        .addEventListener("change", function () {
          let file = this.files[0];
          if (!file) return;

          let imageURL = URL.createObjectURL(file);
          photo.onload = function () {
            photoLoaded = true;
            drawPhotoAndName();
            URL.revokeObjectURL(imageURL);
          };
          photo.onerror = function () {
            alert("이미지를 불러오지 못했습니다.");
            URL.revokeObjectURL(imageURL);
          };
          photo.src = imageURL;
        });

      function drawPhotoAndName() {
        if (!photoLoaded) {
          alert("먼저 사진 파일을 선택하세요.");
          return;
        }

        let name = document.getElementById("userName").value;
        context.clearRect(0, 0, canvas.width, canvas.height);

        // 사진을 캔버스 크기에 맞추어 그린다.
        let scale = Math.min(
          canvas.width / photo.width,
          canvas.height / photo.height,
        );
        let w = photo.width * scale;
        let h = photo.height * scale;
        let x = (canvas.width - w) / 2;
        let y = (canvas.height - h) / 2;
        context.drawImage(photo, x, y, w, h);

        // 이름의 테두리를 먼저 그리고 글자 내부를 채운다.
        context.font = "italic bold 34px Georgia";
        context.textAlign = "center";
        context.textBaseline = "middle";
        context.lineWidth = 3;
        context.strokeStyle = "black";
        context.fillStyle = "purple";
        context.strokeText(name, canvas.width / 2, canvas.height - 30);
        context.fillText(name, canvas.width / 2, canvas.height - 30);
      }
    </script>
  </body>
</html>
```

(1)과 마찬가지로 사진을 먼저 캔버스에 출력한다. 그다음 `strokeText()`로 이름의 테두리를 그리고, `fillText()`로 글자 내부를 채운다. `lineWidth`는 테두리의 굵기를, `strokeStyle`은 테두리 색을 지정한다. 따라서 글자 내부는 보라색이고 테두리는 검은색으로 출력된다.

---

## 5. 폼으로부터 여러 속성을 입력받아 캔버스에 사각형을 그리는 웹 페이지를 작성하라.

**정답:**

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>폼으로 사각형 그리기</title>
    <style>
      .form-area {
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 8px 14px;
        max-width: 520px;
        margin-bottom: 12px;
      }

      .form-area label {
        display: flex;
        justify-content: space-between;
        align-items: center;
        gap: 8px;
      }

      .form-area input[type="number"] {
        width: 100px;
      }

      canvas {
        display: block;
        max-width: 100%;
        background-color: aliceblue;
        border: 1px solid #ddd;
      }
    </style>
  </head>
  <body>
    <h3>폼으로 사각형 그리기</h3>
    <hr />

    <div class="form-area">
      <label>x <input type="number" id="x" value="100" /></label>
      <label>y <input type="number" id="y" value="100" /></label>
      <label>width <input type="number" id="width" value="250" /></label>
      <label>height <input type="number" id="height" value="50" /></label>
      <label
        >선 굵기 <input type="number" id="lineWidth" value="10" min="1"
      /></label>
      <label>선 색 <input type="color" id="lineColor" value="#800080" /></label>
    </div>

    <button type="button" onclick="drawRect()">그리기</button>
    <button type="button" onclick="clearCanvas()">지우기</button>
    <br /><br />

    <canvas id="myCanvas" width="500" height="220"></canvas>

    <script>
      let canvas = document.getElementById("myCanvas");
      let context = canvas.getContext("2d");

      function drawRect() {
        let x = Number(document.getElementById("x").value);
        let y = Number(document.getElementById("y").value);
        let width = Number(document.getElementById("width").value);
        let height = Number(document.getElementById("height").value);
        let lineWidth = Number(document.getElementById("lineWidth").value);
        let lineColor = document.getElementById("lineColor").value;

        if (width < 0 || height < 0 || lineWidth <= 0) {
          alert("너비, 높이, 선 굵기를 올바르게 입력하세요.");
          return;
        }

        context.lineWidth = lineWidth;
        context.strokeStyle = lineColor;
        context.strokeRect(x, y, width, height);
      }

      function clearCanvas() {
        context.clearRect(0, 0, canvas.width, canvas.height);
      }
    </script>
  </body>
</html>
```

1. 폼에서 사각형의 시작 좌표 `x`, `y`, 너비 `width`, 높이 `height`, 선 굵기, 선 색을 입력받는다.
2. 입력한 값은 `document.getElementById()`로 가져오고, 숫자 입력값은 `Number()`로 숫자로 변환한다.
3. `context.lineWidth`에 선 굵기를, `context.strokeStyle`에 선 색을 지정한다.
4. `strokeRect(x, y, width, height)`는 지정한 좌표와 크기로 사각형의 테두리를 그린다.
5. 그리기 버튼을 여러 번 누르면 이전 사각형을 지우지 않고 계속 추가한다. 지우기 버튼은 `clearRect()`로 캔버스 전체를 지운다.

---

## 6. 폼으로부터 여러 속성을 입력받아 캔버스에 원호를 그리는 웹 페이지를 작성하라.

**정답:**

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>폼으로 원호 그리기</title>
    <style>
      .form-area {
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 8px 14px;
        max-width: 540px;
        margin-bottom: 12px;
      }

      .form-area label {
        display: flex;
        justify-content: space-between;
        align-items: center;
        gap: 8px;
      }

      .form-area input[type="number"],
      .form-area select {
        width: 110px;
      }

      canvas {
        display: block;
        max-width: 100%;
        background-color: aliceblue;
        border: 1px solid #ddd;
      }
    </style>
  </head>
  <body>
    <h3>폼으로 원호 그리기</h3>
    <hr />

    <div class="form-area">
      <label>x <input type="number" id="x" value="350" /></label>
      <label>y <input type="number" id="y" value="100" /></label>
      <label
        >반지름 <input type="number" id="radius" value="100" min="1"
      /></label>
      <label
        >방향
        <select id="direction">
          <option value="clockwise">시계방향</option>
          <option value="counterclockwise">반시계방향</option>
        </select>
      </label>
      <label
        >시작각도 <input type="number" id="startAngle" value="180"
      /></label>
      <label>끝각도 <input type="number" id="endAngle" value="360" /></label>
      <label
        >선 굵기 <input type="number" id="lineWidth" value="20" min="1"
      /></label>
      <label>선 색 <input type="color" id="lineColor" value="#663300" /></label>
    </div>

    <button type="button" onclick="drawArc()">그리기</button>
    <button type="button" onclick="clearCanvas()">지우기</button>
    <br /><br />

    <canvas id="myCanvas" width="500" height="250"></canvas>

    <script>
      let canvas = document.getElementById("myCanvas");
      let context = canvas.getContext("2d");

      function drawArc() {
        let x = Number(document.getElementById("x").value);
        let y = Number(document.getElementById("y").value);
        let radius = Number(document.getElementById("radius").value);
        let startAngle = Number(document.getElementById("startAngle").value);
        let endAngle = Number(document.getElementById("endAngle").value);
        let lineWidth = Number(document.getElementById("lineWidth").value);
        let color = document.getElementById("lineColor").value;
        let counterclockwise =
          document.getElementById("direction").value === "counterclockwise";

        if (radius <= 0 || lineWidth <= 0) {
          alert("반지름과 선 굵기는 0보다 큰 값이어야 합니다.");
          return;
        }

        // 각도를 라디안으로 변환한다.
        let start = (startAngle * Math.PI) / 180;
        let end = (endAngle * Math.PI) / 180;

        context.beginPath();
        context.lineWidth = lineWidth;
        context.strokeStyle = color;
        context.arc(x, y, radius, start, end, counterclockwise);
        context.stroke();
      }

      function clearCanvas() {
        context.clearRect(0, 0, canvas.width, canvas.height);
      }
    </script>
  </body>
</html>
```

1. 폼에서 원호의 중심 좌표 `x`, `y`, 반지름, 시작각도, 끝각도, 방향, 선 굵기, 선 색을 입력받는다.
2. `arc()` 메소드의 각도 인수는 라디안이므로, 사용자가 입력한 도 단위의 각도에 `Math.PI / 180`을 곱해 라디안으로 변환한다.
3. `arc(x, y, radius, start, end, counterclockwise)`의 마지막 인수가 `false`이면 시계방향, `true`이면 반시계방향으로 원호를 그린다.
4. `lineWidth`와 `strokeStyle`로 원호의 선 굵기와 색을 지정하고 `stroke()`로 그린다.
5. 그리기 버튼을 누를 때마다 원호가 추가되며, 지우기 버튼을 누르면 캔버스 전체가 지워진다.

---

## 7. 캔버스에 마우스를 누르고 드래그하여 마우스를 놓으면 선이 그려지는 웹 페이지를 작성하라. 마우스를 누르면 이전 선은 지워지고 드래그하여 마우스를 놓으면 새 선이 그려진다. 마우스를 드래그하는 동안 선의 모양이 계속 보이도록 하라.

**정답:**

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>mousedown과 mouseup으로 선 그리기</title>
    <style>
      canvas {
        background-color: aliceblue;
        border: 1px solid #ddd;
        cursor: crosshair;
      }
    </style>
  </head>
  <body>
    <h3>mousedown과 mouseup으로 선 그리기</h3>
    <hr />
    <canvas id="myCanvas" width="500" height="220"></canvas>

    <script>
      let canvas = document.getElementById("myCanvas");
      let context = canvas.getContext("2d");
      let dragging = false;
      let startX = 0;
      let startY = 0;
      let endX = 0;
      let endY = 0;

      function getMousePosition(event) {
        let rect = canvas.getBoundingClientRect();
        return {
          x: ((event.clientX - rect.left) * canvas.width) / rect.width,
          y: ((event.clientY - rect.top) * canvas.height) / rect.height,
        };
      }

      function drawLine(x, y) {
        context.clearRect(0, 0, canvas.width, canvas.height);
        context.beginPath();
        context.moveTo(startX, startY);
        context.lineTo(x, y);
        context.strokeStyle = "purple";
        context.lineWidth = 2;
        context.stroke();
      }

      canvas.addEventListener("mousedown", function (event) {
        let pos = getMousePosition(event);
        dragging = true;
        startX = pos.x;
        startY = pos.y;
        endX = pos.x;
        endY = pos.y;

        // 마우스를 누르는 순간 이전 선을 지운다.
        context.clearRect(0, 0, canvas.width, canvas.height);
      });

      canvas.addEventListener("mousemove", function (event) {
        if (!dragging) return;

        let pos = getMousePosition(event);
        endX = pos.x;
        endY = pos.y;

        // 드래그하는 동안 현재 선을 계속 다시 그린다.
        drawLine(endX, endY);
      });

      window.addEventListener("mouseup", function (event) {
        if (!dragging) return;

        let rect = canvas.getBoundingClientRect();
        let x = ((event.clientX - rect.left) * canvas.width) / rect.width;
        let y = ((event.clientY - rect.top) * canvas.height) / rect.height;

        // 캔버스 밖에서 마우스를 놓은 경우 마지막 위치를 캔버스 경계 안으로 제한한다.
        endX = Math.max(0, Math.min(canvas.width, x));
        endY = Math.max(0, Math.min(canvas.height, y));
        drawLine(endX, endY);
        dragging = false;
      });
    </script>
  </body>
</html>
```

1. `mousedown` 이벤트가 발생하면 `dragging`을 `true`로 바꾸고 선의 시작 좌표를 저장한다. 이때 `clearRect()`로 이전에 그린 선을 지운다.
2. 마우스를 누른 채 움직이면 `mousemove` 이벤트가 발생한다. `dragging`이 `true`인 경우 시작점과 현재 마우스 위치를 연결하는 선을 그린다.
3. 드래그하는 동안 선의 모양이 계속 보이도록 `mousemove`가 발생할 때마다 캔버스를 지우고 현재 선을 다시 그린다.
4. 마우스 버튼을 놓으면 `mouseup` 이벤트가 발생하고, 마지막 위치까지 선을 그린 후 `dragging`을 `false`로 바꾼다.
5. 마우스를 누를 때마다 이전 선을 지우므로 캔버스에는 마지막으로 그린 선 하나만 남는다.

---

## 8. 선의 굵기와 선 색을 선택하고 마우스 드래깅으로 캔버스에 그림을 그릴 수 있는 웹 페이지를 작성하라. 예제 11-11을 참고하라.

**정답:**

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>캔버스에 마우스 드래깅으로 그림 그리기</title>
    <style>
      canvas {
        display: block;
        background-color: aliceblue;
        border: 1px solid #ddd;
        cursor: crosshair;
        max-width: 100%;
      }

      label {
        margin-right: 12px;
      }
    </style>
  </head>
  <body>
    <h3>마우스를 누른 채 드래깅하여 그림을 그려 보세요</h3>
    <hr />

    <label>
      선 굵기:
      <input type="number" id="lineWidth" value="2" min="1" max="50" />
    </label>
    <label>
      선 색:
      <input type="color" id="lineColor" value="#000000" />
    </label>
    <br /><br />

    <canvas id="myCanvas" width="500" height="350"></canvas>

    <script>
      let canvas = document.getElementById("myCanvas");
      let context = canvas.getContext("2d");
      let drawing = false;
      let lastX = 0;
      let lastY = 0;

      context.lineCap = "round";
      context.lineJoin = "round";

      function getMousePosition(event) {
        let rect = canvas.getBoundingClientRect();
        return {
          x: ((event.clientX - rect.left) * canvas.width) / rect.width,
          y: ((event.clientY - rect.top) * canvas.height) / rect.height,
        };
      }

      canvas.addEventListener("mousedown", function (event) {
        let pos = getMousePosition(event);
        drawing = true;
        lastX = pos.x;
        lastY = pos.y;
      });

      canvas.addEventListener("mousemove", function (event) {
        if (!drawing) return;

        let pos = getMousePosition(event);
        context.beginPath();
        context.moveTo(lastX, lastY);
        context.lineTo(pos.x, pos.y);
        context.lineWidth = Number(document.getElementById("lineWidth").value);
        context.strokeStyle = document.getElementById("lineColor").value;
        context.stroke();

        lastX = pos.x;
        lastY = pos.y;
      });

      window.addEventListener("mouseup", function () {
        drawing = false;
      });

      canvas.addEventListener("mouseleave", function () {
        drawing = false;
      });
    </script>
  </body>
</html>
```

1. 선 굵기는 숫자 입력 창에서, 선 색은 `input type="color"`에서 선택한다.
2. `mousedown` 이벤트에서 마우스가 눌렸다는 상태를 `drawing = true`로 설정하고 시작 좌표를 저장한다.
3. `mousemove` 이벤트가 발생할 때 `drawing`이 `true`이면 이전 좌표와 현재 좌표를 `lineTo()`로 연결하여 선을 그린다.
4. 현재 좌표를 다음 선분의 시작 좌표로 저장하므로 마우스 움직임을 따라 연속된 자유 곡선이 만들어진다.
5. `mouseup` 또는 `mouseleave` 이벤트가 발생하면 `drawing = false`로 바꾸어 그리기를 멈춘다.
6. 이 문제는 이전 선을 지우지 않으므로 마우스로 그린 선들이 캔버스에 계속 남는다.

---

## 9. 마우스를 누르지 않고 자유롭게 움직이면서 캔버스에 그림을 그리는 웹 페이지를 작성하라.

**정답:**

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>mousemove로 자유롭게 그리기</title>
    <style>
      canvas {
        display: block;
        background-color: aliceblue;
        border: 1px solid #ddd;
        cursor: crosshair;
        max-width: 100%;
      }

      label {
        margin-right: 12px;
      }
    </style>
  </head>
  <body>
    <h3>mousemove로 자유롭게 그리세요</h3>
    <hr />

    <label>
      선 굵기:
      <input type="number" id="lineWidth" value="5" min="1" max="50" />
    </label>
    <label>
      선 색:
      <input type="color" id="lineColor" value="#669933" />
    </label>
    <br /><br />

    <canvas id="myCanvas" width="500" height="300"></canvas>

    <script>
      let canvas = document.getElementById("myCanvas");
      let context = canvas.getContext("2d");
      let drawing = false;
      let lastX = 0;
      let lastY = 0;

      context.lineCap = "round";
      context.lineJoin = "round";

      function getMousePosition(event) {
        let rect = canvas.getBoundingClientRect();
        return {
          x: ((event.clientX - rect.left) * canvas.width) / rect.width,
          y: ((event.clientY - rect.top) * canvas.height) / rect.height,
        };
      }

      // 마우스가 캔버스 안으로 들어오면 그리기를 시작할 준비를 한다.
      canvas.addEventListener("mouseover", function (event) {
        let pos = getMousePosition(event);
        lastX = pos.x;
        lastY = pos.y;
        drawing = true;
      });

      // 마우스가 움직일 때마다 이전 위치와 현재 위치를 연결한다.
      canvas.addEventListener("mousemove", function (event) {
        if (!drawing) return;

        let pos = getMousePosition(event);
        context.beginPath();
        context.moveTo(lastX, lastY);
        context.lineTo(pos.x, pos.y);
        context.lineWidth = Number(document.getElementById("lineWidth").value);
        context.strokeStyle = document.getElementById("lineColor").value;
        context.stroke();

        lastX = pos.x;
        lastY = pos.y;
      });

      // 마우스가 캔버스 밖으로 나가면 선 그리기를 중단한다.
      canvas.addEventListener("mouseout", function () {
        drawing = false;
      });
    </script>
  </body>
</html>
```

1. 이 문제는 마우스 버튼을 누르지 않아도 마우스를 움직이면 선이 그려진다.
2. `mouseover` 이벤트가 발생하면 캔버스 안으로 들어온 마우스의 좌표를 저장하고 그리기를 시작할 수 있도록 `drawing`을 `true`로 설정한다.
3. `mousemove` 이벤트에서 이전 좌표와 현재 좌표를 연결하여 선을 그린다. 선을 그린 뒤 현재 좌표를 `lastX`, `lastY`에 저장한다.
4. `mouseout` 이벤트가 발생하면 `drawing`을 `false`로 설정하여 캔버스 밖으로 나간 뒤에는 선이 그려지지 않도록 한다.
5. 선 굵기와 선 색은 폼에서 선택한 값을 사용한다.

| 이벤트      | 역할                                        |
| ----------- | ------------------------------------------- |
| `mouseover` | 마우스가 캔버스 안으로 들어오면 그리기 준비 |
| `mousemove` | 마우스가 움직일 때 선 그리기                |
| `mouseout`  | 마우스가 캔버스 밖으로 나가면 그리기 중단   |
