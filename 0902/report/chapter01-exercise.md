# 1장. 웹 프로그래밍과 HTML5 개요 - 연습문제

## 이론문제

### 1. 인터넷에 대한 설명 중 맞는 것은?

**정답: ③**

인터넷에 연결된 컴퓨터는 `210.1.1.2`처럼 0~255 범위의 숫자 4개로 이루어진 IP 주소를 가진다.
①은 PC 외에 스마트폰·TV 등 다양한 기기가 연결되므로 틀리고, ②는 인터넷 자체가 아니라 웹이 서버-클라이언트로 동작하는 것이며, ④는 인터넷이 1969년 ARPANET에서 시작되어 컴퓨터 개발 시점과 다르다.

### 2. 웹에 대한 설명 중 틀린 것은?

**정답: ②**

웹 서버는 원격으로 관리되는 경우가 많아 키보드·마우스·모니터가 없는 형태로도 운영된다.

### 3. 웹 브라우저들이 세상에 나온 순서를 시간 순으로 나열하라.

**정답:**

`WorldWideWeb → Netscape Navigator → Internet Explorer → Opera → Safari → Firefox → Chrome`

| 순서 | 브라우저 | 발표 연도 |
|:---:|---|:---:|
| 1 | WorldWideWeb | 1990 |
| 2 | Netscape Navigator | 1994 |
| 3 | Internet Explorer | 1995 |
| 4 | Opera | 1996 |
| 5 | Safari | 2003 |
| 6 | Firefox | 2004 |
| 7 | Chrome | 2008 |

### 4. 처음으로 웹 브라우저를 만든 사람은?

**정답: ① 팀 버너스리(Tim Berners-Lee)**

CERN에서 근무하던 팀 버너스리가 1990년에 최초의 웹 브라우저를 만들었다.

### 5. 최초로 만들어진 웹 브라우저의 이름은 무엇인가?

**정답: WorldWideWeb**

이후 웹(World Wide Web) 자체와 이름이 혼동되는 것을 피하기 위해 Nexus로 이름을 바꾸었다.

### 6. 웹 페이지를 작성할 때 다음 언어의 역할은 무엇인가?

| 언어 | 역할 |
|---|---|
| **HTML** | 웹 페이지의 **구조(내용)** 를 작성한다. 제목, 문단, 이미지, 표, 입력 양식 등 어떤 요소가 들어가는지 정의한다. |
| **CSS** | 웹 페이지의 **모양(스타일)** 을 꾸민다. 색, 크기, 글꼴, 배치, 여백 등 화면에 보이는 형태를 지정한다. |
| **JavaScript** | 웹 페이지의 **동작(사용자 인터페이스)** 을 담당한다. 사용자 입력에 반응하고 HTML 요소나 CSS를 동적으로 변경한다. |

### 7. 전자 문서와 html 웹 문서의 차이점을 설명한 것 중 틀린 것은?

**정답: ③**

하이퍼링크는 전자 문서가 아니라 웹에서 시작된 개념으로, 문서와 문서를 연결하는 웹의 핵심 기능이다.

### 8. 웹 브라우저가 처리하는 과정의 빈칸을 채워라.

| 과정 | 내용 |
|---|---|
| 과정 1) | 웹 브라우저는 **www.univ.ac.kr 웹 서버** 에 접속한다. |
| 과정 2) | 웹 브라우저는 **score.html 파일(웹 페이지)** 를 보내 줄 것을 웹 서버에 요청한다. |
| 과정 3) | 웹 브라우저는 받은 웹 페이지를 해독하여 화면에 출력한다. |

### 9. 웹의 기본적인 성공 요인에 해당하지 않는 것은?

**정답: ④**

브라우저마다 서로 다른 플러그인을 만들어 경쟁한 것은 호환성을 떨어뜨린 요인이며, 오히려 HTML5가 등장하게 된 배경이다.

### 10. HTML5가 출현하게 된 배경이 아닌 것은?

**정답: ①**

이미지는 HTML4에서도 `<img>` 태그로 지원했다. HTML5에서 새로 표준으로 지원한 것은 오디오와 비디오다.

### 11. 음악을 연주하는 HTML5 문서에 대해 잘못 말한 것은?

**정답: ③**

HTML5는 기기에 독립적인 표준이므로 PC용으로 작성한 문서라도 HTML5를 지원하는 스마트폰 브라우저에서 동일하게 재생된다.

---

## 실습문제

### 1. 오류 3개를 찾아 수정하라

| 위치 | 오류 | 수정 |
|---|---|---|
| 1행 | `<DOCTYPE html>` | `<!DOCTYPE html>` |
| `</head>` 앞 | `</style>` 종료 태그 누락 | `</style>` 추가 |
| CSS | `span { color = blue; ... }` | `span { color : blue; ... }` |

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>오류를 찾으세요</title>
<style>
    h3 { text-align : center; color : darkred; }
    span { color : blue; font-size : 20px; }
</style>
</head>
<body>
<h3>Elvis Presley</h3>
He was an American singer and actor. In November 1956,
he is often referred to as "<span>the King of Rock and Roll</span>".
</body>
</html>
```

### 2. 오류 3개를 찾아 수정하라

| 위치 | 오류 | 수정 |
|---|---|---|
| 3행 | `<body>` (`<head>` 자리에 잘못 사용) | `<head>` |
| `<h3>` 종료 | `</h>` | `</h3>` |
| CSS | `text-align : center color : darkred;` | `text-align : center; color : darkred;` |

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>오류를 찾으세요</title>
<style>
    h3 { text-align : center; color : darkred; }
    span { color : blue; font-size : 20px; }
</style>
</head>
<body>
<h3>Elvis Presley</h3>
He was an American singer and actor. In November 1956,
he is often referred to as "<span>the King of Rock and Roll</span>".
</body>
</html>
```

### 3. `<span>` 글자색을 violet으로, `<hr>` 수평선 두께를 10px로 변경

`span`의 `color` 값을 `violet`으로 바꾸고, `hr` 선택자에 `height : 10px`를 지정한다.
`<hr>`은 브라우저 기본 테두리(border)를 가지고 있어 `border : none`으로 없앤 뒤 `background-color`로 색을 채워야 지정한 두께가 그대로 보인다.

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>웹 페이지의 구성 요소</title>
<style>
    body { background-color : mistyrose; }
    h3 { text-align : center; color : darkred; }
    hr { height : 10px; background-color : darkred; border : none; }
    span { color : violet; font-size : 20px; }
</style>
</head>
<body>
<h3>Elvis Presley</h3>
<hr>
He was an American singer and actor. In November 1956,
he made his film debut in <span>Love Me Tender</span>.
He is often referred to as "<span>the King of Rock and Roll</span>".
</body>
</html>
```

### 4. `<span>Love Me Tender</span>`에 마우스를 올리면 자신의 사진이 출력되도록 수정

`<span>`에 `onmouseover`, `onmouseout` 이벤트를 등록하고, 자바스크립트로 `<img>` 요소의 `style.display` 값을 `block`과 `none`으로 바꾼다.
사진 파일은 HTML 파일과 같은 폴더에 두고 `src`에 파일 이름만 적으면 된다.

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>웹 페이지의 구성 요소</title>
<style>
    body { background-color : mistyrose; }
    h3 { text-align : center; color : darkred; }
    hr { height : 10px; background-color : darkred; border : none; }
    span { color : violet; font-size : 20px; }
    #myPhoto { display : none; width : 150px; }
</style>
</head>
<body>
<h3>Elvis Presley</h3>
<hr>
<img id="myPhoto" src="image.jpg" alt="내 사진">
He was an American singer and actor. In November 1956,
he made his film debut in
<span onmouseover="document.getElementById('myPhoto').style.display='block'"
      onmouseout="document.getElementById('myPhoto').style.display='none'">Love Me Tender</span>.
He is often referred to as "<span>the King of Rock and Roll</span>".
</body>
</html>
```
