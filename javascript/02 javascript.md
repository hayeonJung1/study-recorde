# javascript

### 자바스크립트 선언

---

🔹 `<script>`는 ‘src’와 ‘type’ 속성을 사용하여 js를 선언

🔹 src : 외부의 js 파일을 html문서에 포함할 때 사용, 생략 가능

🔹 type : 미디어 타입을 지정할 때 사용( js 코드는 ‘text/javascript’로 지정) → html5에서는 디폴트로 지정되어 있기 때문에 선언해줄 필요는 없음 하위 호완성을 위해서는 적어주는 게 좋음

🔹 head나 body 안에 어느 곳이나 선언 가능

body 안의 끝 부분에 script 태그를 둘 것을 권장

**내부 선언**

```jsx
<head>
	<meta charset="UTF-8">
	<title>JavaScript 선언</title>
	<script type="text/javascript">
		document.write("환영합니다."
	</script>
</head>
```

**외부 선언**

```jsx
<head>
	<meta charset="UTF-8">
	<title>JavaScript 선언</title>
	<script src="hello.js" type="text/javascript"></script>
</head>
```

### 주석

---

```jsx
// 한 줄 주석

/*
	여러 줄 주석
*/
```

### 주의 사항

---

🔹 자바스크립트는 대, 소문자를 구분한다.

🔹 코드 한 줄을 작성한 후에는 세미콜론(;)을 사용하는 것이 좋다.

🔹 코드를 작성할 때는 한 줄에 한 문장만 작성하는 것이 가독성에 좋다.

🔹 문자형 데이터를 작성할 때는 큰따옴표와 작은따옴표의 겹침 오류를 주의