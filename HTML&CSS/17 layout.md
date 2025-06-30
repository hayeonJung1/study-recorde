# layout

### div 요소 레이아웃

```css
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>div 요소 레이아웃</title>
  </head>
  <style>
    .container {
      width: 1400px;
      margin: 0 auto; /*중앙 정렬*/
    }
    .header {
      height: 60px;
      background-color: #dddddd;
    }
    .sidebar {
      width: 400px;
      height: 300px;
      float: left; /*수평 정렬을 위한*/
      background-color: orange;
    }
    .section {
      width: 1000px;
      height: 300px;
      float: right; /*수평 정렬을 위한*/
      background-color: skyblue;
    }
    .footer {
      clear: both; /*float 해제*/
      height: 60px;
      background-color: #dddddd;
    }
  </style>
  <body>
    <div class="container">
      <div class="header">상단 헤더</div>
      <div class="sidebar">사이드바</div>
      <div class="section">메인 섹션</div>
      <div class="footer">하단 푸터</div>
    </div>
  </body>
</html>

```

### 시멘틱 태그 레이아웃

| 태그 | 설명 |
| --- | --- |
| `<header>` | 상단 헤더의 영역 |
| `<nav>` | 네비게이션 링크인 메뉴, 상단 메뉴, 하단 메뉴 등에 사용 |
| `<section>` | 메인 컨텐츠, 섹션에 사용 |
| `<article>` | 섹션 내의 독립적인 공간에 사용 |
| `<aside>` | 섹션의 좌측 또는 우측의 사이드바에 사용 |
| `<footer>` | 하단 푸터에 사용 |

```css
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>시멘틱 태그 레이아웃</title>
  </head>
  <style>
    .container {
      width: 1400px;
      margin: 0 auto;
    }
    header {
      height: 60px;
      background-color: #dddddd;
    }
    aside {
      width: 400px;
      height: 300px;
      float: left;
      background-color: pink;
    }
    section {
      width: 1000px;
      height: 300px;
      float: right;
      background-color: yellow;
    }
    footer {
      clear: both;
      height: 60px;
      background-color: #dddddd;
    }
    header,
    aside,
    section,
    footer {
      font-size: 20px;
      text-align: center;
      padding-top: 10px;
    }
  </style>
  <body>
    <div class="container">
      <header>header 상단헤더</header>
      <aside>aside 사이드 바</aside>
      <section>section 메인 콘텐츠</section>
      <footer>footer 하단 푸터</footer>
    </div>
  </body>
</html>
```