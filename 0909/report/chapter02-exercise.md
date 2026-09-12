# 2장. HTML5 기본 문서 만들기 - 이론문제

## 1. HTML5 표준에 따라 HTML 페이지에 반드시 있어야 하는 것이 아닌 것은?

**정답: ② `<img>`**

HTML5 문서는 `<!doctype html>` 선언으로 시작하고 `<head>`와 `<body>`로 구성된다. `<img>`는 이미지를 삽입할 때만 사용하는 선택적인 태그이다.

## 2. HTML 언어에서 사용되는 옳은 주석문은?

**정답: ③ `<!-- 이것은 주석문 -->`**

HTML 주석은 `<!--`로 시작해서 `-->`로 끝난다.

## 3. 다음 중 틀린 것은?

```
<Img width='100' height="35" alt=심장 src:shrek.png>
```

**정답: ④ `src:shrek.png`**

속성은 `속성이름="값"` 형식으로 `=`를 사용해야 한다. `src:shrek.png`가 아니라 `src="shrek.png"`로 작성해야 한다.

수정된 태그

```html
<img width="100" height="35" alt="심장" src="shrek.png">
```

## 4. href 속성을 가지지 않는 태그는?

**정답: ① `<iframe>`**

`<iframe>`은 삽입할 페이지를 `src` 속성으로 지정한다. `<a>`, `<area>`, `<base>`는 모두 `href`로 URL을 지정한다.

## 5. target 속성을 가지지 않는 태그는?

**정답: ④ `<img>`**

`target`은 링크로 열린 페이지를 출력할 창을 지정하는 속성이므로 링크 기능이 없는 `<img>`에는 사용할 수 없다.

## 6. src 속성을 가지지 않는 태그는?

**정답: ④ `<div>`**

`<div>`는 여러 태그를 묶는 블록 컨테이너일 뿐 외부 자원을 불러오지 않는다. `<iframe>`, `<embed>`, `<audio>`는 `src`로 자원의 위치를 지정한다.

## 7. 다음 중 블록형 태그가 아닌 것은?

**정답: ④ `<img>`**

`<img>`는 인라인 태그로 앞뒤로 줄바꿈이 일어나지 않고 텍스트와 같은 줄에 출력된다. `<div>`, `<p>`, `<h1>`은 블록형 태그이다.

## 8. 웹 페이지의 제작자를 표현하기 위해 사용되는 태그는?

**정답: ② `<meta>`**

```html
<meta name="author" content="황기태">
```

## 9. 웹 페이지를 만든 이유를 "자바에 대해 알려주려고"라고 적어 놓고자 한다. 가장 적절한 태그는?

**정답: `<meta>` 태그의 description**

```html
<meta name="description" content="자바에 대해 알려주려고">
```

## 10. `<base>` 태그를 이용하여 베이스 URL을 지정하고 두 `<a>` 태그를 간략히 다시 작성하라.

`<head>` 안에 베이스 URL을 지정하면 이후의 상대 주소는 모두 이 URL을 기준으로 해석된다.

```html
<head>
<base href="http://www.mysite.com/html/design/">
</head>
```

```html
<a href="dress.html">옷</a>
<a href="shoes.html">신발</a>
```

## 11. `<ol>`, `<ul>`, `<dl>` 중 어떤 것이 적합한가?

| 경우 | 태그 | 이유 |
|---|:---:|---|
| (1) 유럽 여행에 필요한 물품을 나열할 때 | `<ul>` | 순서와 상관없는 항목의 나열 |
| (2) 출국 수속 과정을 나열할 때 | `<ol>` | 진행 순서가 있는 항목의 나열 |
| (3) 유럽 각 나라들의 특징을 나열할 때 | `<dl>` | 이름과 그에 대한 설명이 짝을 이루는 나열 |

## 12. 링크 텍스트에 대한 디폴트 색

| 상태 | 색 |
|---|---|
| 처음 (방문 전) | 파란색 |
| 방문한 후 | 보라색 |
| 마우스를 누르고 있는 동안 | 빨간색 |

## 13. HTML 페이지에 다른 HTML 페이지를 삽입하기 위해 사용되는 태그는?

**정답: ① `<iframe>`**

`<iframe>`은 현재 페이지 안에 또 하나의 창을 만들어 `src`로 지정한 다른 HTML 페이지를 출력한다.

## 14. 다음은 오류가 있는 HTML5 문서이다. 틀린 부분을 찾아 완성하라.

### (1)

| 오류 | 수정 |
|---|---|
| `<!doctype html>` 선언이 없음 | 문서 맨 앞에 추가 |
| `<body>`, `</body>` 태그가 없음 | 본문 내용을 `<body>`로 감쌈 |

```html
<!doctype html>
<html>
<head><title></title>
</head>
<body>
<h3>나의 이야기</h3>
<hr>
나는 자랑스러운 대한민국의 국민입니다.
</body>
</html>
```

### (2)

| 오류 | 수정 |
|---|---|
| `</br>` 사용 | `<br>`은 닫는 태그가 없는 빈 태그이므로 `</br>` 삭제 |

```html
<!doctype html>
<html>
<head><title></title></head>
<body>
<br>Merry Christmas! Happy New Year!
</body>
</html>
```

## 15. HTML5 문서에 사용하지 않는 것이 바람직한 태그는?

**정답: ③ `<frameset><frame src="1.html"><frame src="2.html"></frameset>`**

`<frameset>`과 `<frame>`은 HTML5에서 폐기된 태그이다. 화면을 나누어 여러 페이지를 출력하려면 `<iframe>`을 사용해야 한다.

## 16. `<source>` 태그를 사용하여 다음 문장을 수정하라.

`src` 속성을 `<audio>`에서 떼어내어 `<source>` 태그로 옮긴다.

```html
<audio controls>
    <source src="hello.mp3" type="audio/mpeg">
    audio를 지원하지 않습니다.
</audio>
```

## 17. 다음에 작성된 HTML 태그의 의도를 자세히 설명하라.

```html
<video width="320" height="240" controls autoplay>
    <source src="bear.mp4" type="video/mp4">
    <source src="bear.ogg" type="video/ogg">
    브라우저가 video 태그를 지원하지 않습니다.
</video>
```

- 가로 320px, 세로 240px 크기의 비디오 화면을 만든다.
- `controls`로 재생, 일시정지, 볼륨 등을 조절하는 제어판을 출력한다.
- `autoplay`로 페이지가 열리면 자동으로 재생한다.
- `<source>`를 두 개 두어, 브라우저가 먼저 `bear.mp4`를 재생하고 mp4 형식을 지원하지 않으면 `bear.ogg`를 재생하도록 한다. 어떤 브라우저에서도 비디오가 재생되게 하려는 의도이다.
- 두 형식을 모두 지원하지 않거나 `<video>` 태그 자체를 지원하지 않는 브라우저에서는 안쪽의 텍스트가 대신 출력된다.
