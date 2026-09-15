# Open Challenge 02 — 컴퓨터 기술 소개 웹 페이지

스마트폰을 소개하는 웹 페이지 `2.html`을 HTML5 태그로 작성한다.

## 요구사항 반영

| 요구사항 | 사용 태그 |
|---|---|
| 웹 페이지 소개 오디오 | `<audio controls>` + `<source>` |
| 리스트 | `<ul>`, `<li>` |
| 표 | `<table>` + `<caption>` |
| 이미지 | `<img>` |
| 목차 링크 → 본문 앵커 | `<a href="#id">` + 제목의 `id` 속성 |
| 새 창/탭으로 열기 | 본문 제목 글자에 `<a target="_blank">` |

## 링크 구조

목차의 항목을 누르면 본문의 해당 위치로 이동하고, 본문 제목인 역사 · 안드로이드 · 아이폰 글자를 누르면 관련 사이트가 새 탭에서 열린다.

제목 태그에 `id`를 주어 앵커 역할을 하게 하고, 그 안의 글자를 `<a>`로 감싸 외부 링크를 연결한다.

```html
<h2 id="history">
    <a href="https://ko.wikipedia.org/wiki/스마트폰" target="_blank">역사</a>
</h2>
```

## 2.html

```html
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="utf-8">
<title>컴퓨터 기술 소개</title>
</head>
<body>

<h1>스마트폰</h1>

<p>
스마트폰은 컴퓨터를 결합한 무선 휴대전화기이다. PC에서 실행되는 운영체제보다 작게 만든 모바일
운영체제를 탑재하여 인터넷 검색, 전자우편, 간단한 문서 편집, 카메라, 오디오 및 비디오 재생 등
PC의 기능을 거의 모두 갖추고 있다.
</p>

<audio controls>
    <source src="smartphone.mp3" type="audio/mpeg">
    이 브라우저는 audio 태그를 지원하지 않습니다.
</audio>

<h2>목차</h2>
<ul>
    <li><a href="#history">역사</a></li>
    <li><a href="#android">안드로이드폰</a></li>
    <li><a href="#iphone">아이폰</a></li>
    <li><a href="#sample">샘플</a></li>
</ul>

<hr>

<h2 id="history">
    <a href="https://ko.wikipedia.org/wiki/스마트폰" target="_blank">역사</a>
</h2>
<p>
최초의 스마트폰은 사이먼(Symon)으로 추정된다. IBM이 개발하여 1993년 미국의 라스베이거스에서 열린
컴덱스에서 컨셉 제품으로 전시하였다. 이후 휴대전화에 인터넷과 운영체제가 결합되면서 오늘날의
스마트폰으로 발전하였다.
</p>

<h2 id="android">
    <a href="https://ko.wikipedia.org/wiki/안드로이드_(운영체제)" target="_blank">안드로이드</a>
</h2>
<p>
안드로이드(영어: Android)는 휴대 전화를 비롯한 휴대용 장치를 위한 운영체제, 미들웨어, 사용자
인터페이스 그리고 표준 응용 프로그램(웹 브라우저, 전자우편 클라이언트, 단문 메시지 서비스(SMS),
멀티미디어 메시지 서비스(MMS) 등)을 포함하고 있는 소프트웨어 스택이다.
</p>

<h2 id="iphone">
    <a href="https://en.wikipedia.org/wiki/IPhone" target="_blank">아이폰</a>
</h2>
<p>
아이폰(영어: iPhone)은 2007년 1월 9일, 애플이 발표한 휴대 전화 시리즈이다. 미국 샌프란시스코에서
열린 맥월드 2007에서 애플의 창업자 중 한명인 스티브 잡스가 발표했다.
</p>

<h2 id="sample">샘플</h2>

<table>
<caption>스마트폰샘플</caption>
<tr>
    <td><img src="phone1.jpg" alt="갤럭시" width="100"></td>
    <td><img src="phone2.jpg" alt="아이폰" width="100"></td>
    <td><img src="phone3.jpg" alt="안드로이드폰" width="100"></td>
    <td><img src="phone4.jpg" alt="윈도우폰" width="100"></td>
    <td><img src="phone5.jpg" alt="루미아" width="100"></td>
</tr>
</table>

<hr>
<p>Copyright 2022 by Kitae</p>

</body>
</html>
```

## 준비할 미디어 파일

`2.html`과 같은 폴더에 둔다.

- `smartphone.mp3` : 웹 페이지를 설명하는 20초 분량 녹음 음성
- `phone1.jpg` ~ `phone5.jpg` : 스마트폰 사진 5장
