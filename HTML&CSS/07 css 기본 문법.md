# CSS

CSS는 Cascading Style Sheet의 약어로 웹 페이지에서 HTML 태그를 보조 하여

웹 페이지를 디자인적으로 꾸미고 페이지의 요소를 화면에 배치하는 역할을 수행한다.

### CSS 기본 문법

---

```css
selector{property: property value;}
```

- **선택자(selector)**
    
    CSS를 적용하고자 하는 HTML요소
    
- **속성(Property)**
    
    여러 개의 속성을 연속해서 지정할 수 있으며 세미콜론(;)으로 구분
    
- **속성 값(Property Value)**
    
    어떻게 꾸밀 지 속성 값 입력
    

### CSS 선언 방법

---

1. **Inline - 인라인 방식**
    
    HTML 태그 안에 style 속성에 직접 적용하는 방법
    
    ```css
    <body>
    	<p style="height: 100px; color: blue"></p>
    </body>
    ```
    
2. **Internal - 내부 스타일 방식**
    
    HTML 파일안에 `<style> </style>` 태그를 이용하여 속성을 지정하는 방법
    
    ```css
    <head> 
      <style> 
        p{
    	    height: 100px;
    	    color: blue
    		  } 
      </style> 
    </head>
    ```
    
3. **External - 외부 스타일 방식 (주로 사용되는 방법)**
    
    CSS파일을 따로 작성하고 그 파일을 link하여 사용하는 방법
    
    ```css
    <head> 
      <link href="style.css" rel="stylesheet" type="text/css"> 
    </head>
    ```
    

### CSS 주석

---

```html
/* 한줄 주석 */

/*
 여러줄
 주석
*/
```