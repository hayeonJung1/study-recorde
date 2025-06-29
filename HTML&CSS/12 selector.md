# selector

```css
selector{ property: value; property: value;,...}
```

### 전체 선택자(*)

🔹 HTML 요소 전체를 선택하는 선택자

```css
*{
	/*css code*/
}
```

### tag 선택자

🔹 주어진 이름의 태그를 선택하는 선택자

```css
header {
    /*header css code*/
}
```

### class 선택자

🔹 주어진 이름의 클래스를 선택하는 선택자

🔹 . 을 붙여 클래스임을 구분

```css
/*html*/
<p class="name">
  hello!
</p>

/*css*/
.name {
    color:green;
}
```

### id 선택자

🔹 주어진 이름의 아이디를 선택하는 선택자

🔹 #을 붙여 아이디임을 구분 → 유일한 값으로

```css
/*html*/
<h1 id="title">
  제목
</h1>

/*css*/
#title {
    color:red;
}
```

### 하위 선택자

🔹 하위의 모든 지정 태그의 영역 선택

```css
div p{
    /*p css code*/
}
```

### 속성 선택자

🔹 지정된 속성을 갖는 모든 요소를 선택

```css
a[href]{     
		/*css code*/
}
input[text]{
    /*css code*/
}
```

### 자손, 자식, 동위 선택자

| selector | 표시 | 설명 |
| --- | --- | --- |
| 자손(=후손 =하위) 선택자 | 공백 | 조상 요소 하위의 모든 요소 |
| 자식 선택자(주로 많이 사용) | > | 부모 요소 하위의 자식 요소 |
| 인접 형제 선택자 | + | 동일한 부모의 요소를 갖는 자식 요소 |
| 일반 형제 선택자 | - | 형제 관계를 갖는 요소 중에서 다음에 나오는 모든 동생 요소 |