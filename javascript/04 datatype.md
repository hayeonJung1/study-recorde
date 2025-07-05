# 기본 타입

타입(data type)이란 프로그램에서 다룰 수 있는 값의 종류를 의미

자바스크립트의 기본 타입은 크게 원시 타입과 객체 타입으로 구분

### 원시 타입(primitive type)

---

**🔸 숫자(number)**

자바스크립트는 정수와 실수를 따로 구분하지 않고, 모든 수를 실수 하나로만 표현

또한, 매우 큰 수나 매우 작은 수를 표현할 경우에는 e 표기법을 사용할 수 있다.

```jsx
var first = 10;
var second = 10.00;
var third = 10e6;   // 10000000
var fourth = 10e-6; // 0.00001
```

**🔸 문자열(string)**

큰따옴표는 작은따옴표로 둘러싸인 문자열에만 포함될 수 있으며, 작은따옴표는 큰따옴표로 둘러싸인 문자열에만 포함될 수 있다.

```jsx
var first = "홍길동";      // 큰따옴표를 사용한 문자열
var second = '홍길동';     // 작은따옴표를 사용한 문자열
var third = "이름은 '홍길동'입니다."  // 작은따옴표는 큰따옴표로 둘러싸인 문자열에만 포함될 수 있음.
var fourth = '이름은 "홍길동"입니다.' // 큰따옴표는 작은따옴표로 둘러싸인 문자열에만 포함될 수 있음.
```

🔸 **불리언(boolean)**

참(true)과 거짓(false)를 표현

**🔸 심볼(symbol)**

ECMAScript 6부터 새롭게 추가된 타입이다.

유일하고 변경할 수 없는 타입으로, 객체의 프로퍼티를 위한 식별자로 사용할 수 있다.

```jsx
var sym = Symbol("javascript");  // symbol 타입
var symObj = Object(sym);        // object 타입
```

**🔸 undefined**

### 객체 타입(object type)

---

**🔸 객체(object)**

자바스크립트의 기본 타입은 객체이다.

객체란 실생활에서 우리가 인식할 수 있는 사물로 이해할 수 있다.

여러 프로퍼티나 메소드를 같은 이름으로 묶어놓은 일종의 집합체이다.

```jsx
var dog = { name: "해피", age: 3 }; // 객체의 생성
// 객체의 프로퍼티 참조
document.getElementById("result").innerHTML =
    "강아지의 이름은 " + dog.name + "이고, 나이는 " + dog.age + "살 입니다.";
```

### typeof 연산자

---

피연산자의 타입을 반환하는 피연산자가 단 하나뿐인 연산자

```jsx
typeof 10;        // number 타입
typeof "문자열";  // string 타입
typeof true;      // boolean 타입
typeof undefined; // undefined 타입
typeof null;      // object 타입
```

### null, undefined

---

자바스크립트에서 null이란 object 타입이며, 아직 ‘값’이 정해지지 않은 것을 의미

undefined란 null과는 달리 ‘타입’이 정해지지 않은 것을 의미

자바스크립트에서 undefined는 초기화되지 않은 변수나 존재하지 않는 값에 접근할 때 반환된다.

```jsx
var num;          // 초기화하지 않았으므로 undefined 값을 반환함.
var str = null;   // object 타입의 null 값
typeof secondNum; // 정의되지 않은 변수에 접근하면 undefined 값을 반환함.
```

null과 undefined는 동등 연산자(==)와 일치 연산자(===)로 비교할 때 결과값이 다르므로 주의해야 한다.

```jsx
null ==  undefined; // true
null === undefined; // false
```