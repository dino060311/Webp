# 2장 HTML5 기본 문서 만들기 - 실습문제

## 1. 문자 엔터티를 이용한 페이지

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="utf-8" />
    <title>산길</title>
  </head>
  <body>
    <h3>산길</h3>
    <hr />
    <p>
      오늘 아침 일찍 산에 올랐다. 아침 온도는 15&deg;이었다. 가지고 간 물의
      &frac12;을 마셨다. 한참 올라 가는 도중에 약수터를 가리키는 &#9833; 사인이
      보였다. 불현듯 양두중 님의 산길이란 시에 곡을 붙인 박태준의 가곡&#9834;이
      생각이 났다.
    </p>
    <small>
      <pre>
산길을 간다.
</pre
      >
    </small>
    <p>&copy; Copyright(c) 황기태 All rights reserved. &#9742; 010-0000-9999</p>
  </body>
</html>
```

---

## 2. 리스트를 가진 페이지

### (1) 도시 소개

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="utf-8" />
    <title>도시 소개</title>
  </head>
  <body>
    <h3>도시 소개</h3>
    <hr />
    <dl>
      <dt>California</dt>
      <dd>맑고 화창한 날씨가 좋고 태평양의 아름다운 해변을 가진 멋진 주</dd>
      <dt>Florida</dt>
      <dd>
        미국의 동남부에 위치한 주로서 많은 휴양 도시가 있고 미국의 최남단이
        연결된 아름다운 주
      </dd>
      <dt>Texas</dt>
      <dd>드넓은 목장들이 있어 텍사스 바베큐로 유명하고 석유가 생산되는 주</dd>
    </dl>
  </body>
</html>
```

### (2) 살빼는 방법

순서가 중요하지 않은 나열이고 항목 앞에 점(•)이 붙어 있으므로 순서 없는 리스트 `<ul>`을 사용한다.

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="utf-8" />
    <title>살빼는 방법</title>
  </head>
  <body>
    <h3>살빼는 방법</h3>
    <hr />
    <ul>
      <li>고기를 많이 먹는 고기 다이어트</li>
      <li>채소를 많이 먹는 채소 다이어트</li>
      <li>적게 먹고 운동하는 운동 다이어트</li>
    </ul>
  </body>
</html>
```

---

## 3. 셀카 사진 페이지 (prac2-03.html)

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="utf-8" />
    <title>나의 셀카</title>
  </head>
  <body>
    <h3>나의 셀카</h3>
    <hr />
    <table>
      <caption>
        나의 셀카
      </caption>
      <tr>
        <td><img src="selfie1.jpg" alt="셀카1" height="150" /></td>
        <td><img src="selfie2.jpg" alt="셀카2" height="150" /></td>
        <td><img src="selfie3.jpg" alt="셀카3" height="150" /></td>
      </tr>
    </table>
  </body>
</html>
```

---

## 4. 표 작성

### (1) 학생 신체 검사 표

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="utf-8" />
    <title>학생 신체 검사</title>
  </head>
  <body>
    <h3>신체 검사</h3>
    <hr />
    <table border="1">
      <caption>
        학생 신체 검사 표
      </caption>
      <tr>
        <th>이름</th>
        <th>키</th>
        <th>체중</th>
        <th>시력</th>
      </tr>
      <tr>
        <td>황기태</td>
        <td>179</td>
        <td>67</td>
        <td>1.0</td>
      </tr>
      <tr>
        <td>이재문</td>
        <td>177</td>
        <td>77</td>
        <td>2.0</td>
      </tr>
      <tr>
        <td>정인환</td>
        <td>189</td>
        <td>87</td>
        <td>1.2</td>
      </tr>
      <tr>
        <th>평균</th>
        <th>181</th>
        <th>77</th>
        <th>1.3</th>
      </tr>
    </table>
  </body>
</html>
```

### (2) 과일 수입 표

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="utf-8" />
    <title>과일 수입</title>
  </head>
  <body>
    <h3>과일 수입</h3>
    <hr />
    <table border="1">
      <caption>
        과일 수입 표
      </caption>
      <tr>
        <th>사과</th>
        <th>바나나</th>
        <th>망고</th>
      </tr>
      <tr>
        <td><img src="apple.jpg" alt="사과" width="100" /></td>
        <td><img src="banana.jpg" alt="바나나" width="100" /></td>
        <td><img src="mango.jpg" alt="망고" width="100" /></td>
      </tr>
      <tr>
        <th>페루</th>
        <th>필리핀</th>
        <th>호주</th>
      </tr>
    </table>
  </body>
</html>
```

---

## 5. 참조 사이트 링크 페이지

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="utf-8" />
    <title>웹 프로그래밍 참조 사이트</title>
  </head>
  <body>
    <h3>웹 프로그래밍 참조 사이트</h3>
    <hr />
    <ul>
      <li>
        <a
          href="https://www.w3.org/wiki/CSS/Properties/color/keywords"
          target="_blank"
          >CSS 색깔 이름과 값</a
        >
      </li>
      <li>
        <a href="https://dev.w3.org/html5/html-author/charref" target="_blank"
          >문자 엔터티 코드 사이트</a
        >
      </li>
      <li>
        <a href="http://www.webprogramming.co.kr" target="_blank"
          >웹프로그래밍 사이트</a
        >
      </li>
    </ul>
  </body>
</html>
```

---

## 6. iframe 2개로 구성한 페이지

### 왼쪽에 넣을 메뉴 페이지

3개의 링크 모두 `target="viewer"`로 지정하여 오른쪽 iframe에 출력되게 한다.

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="utf-8" />
    <title>참조 사이트 메뉴</title>
  </head>
  <body>
    <h4>웹 프로그래밍 참조 사이트</h4>
    <ul>
      <li>
        <a
          href="https://www.w3.org/wiki/CSS/Properties/color/keywords"
          target="viewer"
          >CSS 색깔 이름과 값</a
        >
      </li>
      <li>
        <a href="https://dev.w3.org/html5/html-author/charref" target="viewer"
          >문자 엔터티 코드 사이트</a
        >
      </li>
      <li>
        <a href="http://www.webprogramming.co.kr" target="viewer"
          >웹프로그래밍 사이트</a
        >
      </li>
    </ul>
  </body>
</html>
```

### 본 페이지 (prac2-06.html)

왼쪽 iframe의 폭은 250픽셀, 오른쪽 iframe의 폭은 500픽셀로 지정한다.

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="utf-8" />
    <title>웹 프로그래밍 참조 사이트</title>
  </head>
  <body>
    <h3>웹 프로그래밍 참조 사이트</h3>
    <hr />
    <iframe src="prac2-06-menu.html" width="250" height="300"></iframe>
    <iframe
      name="viewer"
      src="http://www.webprogramming.co.kr"
      width="500"
      height="300"
    ></iframe>
  </body>
</html>
```

---

## 7. 애국가를 연주하는 페이지

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="utf-8" />
    <title>애국가 가사</title>
  </head>
  <body>
    <h3>애국가 가사</h3>
    <hr />
    <p>
      동해물과 백두산이 마르고 닳도록 하나님이<br />
      보우하사 우리나라 만세 무궁화 삼천리 화려<br />
      강산 대한사람 대한으로 길이 보전하세.
    </p>
    <audio src="anthem.mp3" controls>audio를 지원하지 않습니다.</audio>
  </body>
</html>
```

---

## 8. 자기 소개 페이지

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="utf-8" />
    <title>자기 소개</title>
  </head>
  <body>
    <h3>자기 소개</h3>
    <hr />
    <p>
      안녕하세요. 제 이름은 빅버드예요. 저는 세스미 스트리트에 살고 있어요. 저는
      편지를 배달하는 일을 해요. 반가운 소식을 여러분에게 전해 주죠. 그리고
      오늘, 희망의 기쁜 소식을 여러 분에게 전해주려고 해요. 명품 HTML5 CSS3
      웹프로그래밍! 정 말 멋진 책이지 않아요? 호호호... 다음에 또 봐요. 안녕~~
    </p>
    <video src="intro.mp4" width="280" controls>
      브라우저가 video 태그를 지원하지 않습니다.
    </video>
  </body>
</html>
```
