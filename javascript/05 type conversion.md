# type conversion

### 타입 변환

---

자바스크립트의 변수는 타입이 정해져 있지 않으며, 같은 변수에 다른 타입의 값을 다시 대입할 수도 있다.

```jsx
var num=20; //number type의 20
num="이십" //string type의 "이십"
// var num; 변수의 재선언은 불가 재선언문은 무시된다.
```

### 묵시적 타입 변환(implicit type conversion)

---

자바스크립트는 특정 타입의 값을 기대하는 곳에 다른 타입의 값이 오면, 자동으로 타입을 변환하여 사용한다.

```jsx
10 + "문자열"; // 문자열 연결을 위해 숫자 10이 문자열로 변환됨.
"3" * "5";     // 곱셈 연산을 위해 두 문자열이 모두 숫자로 변환됨.
1 - "문자열";  // 숫자로 변환될 수 없는 문자열이므로 NaN값 반환
```

🔸 NaN은 Not a Number의 축약형을, 정의되지 않은 값이나 표현할 수 없는 값이라는 의미

### 명시적 타입 변환(explicit type convertion)

---

자바스크립트에서는 묵시적 타입 변환을 많이 사용하지만, 명시적으로 타입을 변환하는 방법도 제공한다.

🔸 Number()

🔸 String()

🔸 Bollean()

🔸 Object()

🔸 parseInt()

🔸 parseFloat()

```jsx
Number("10"); // 숫자 10
String(true); // 문자열 "true"
Boolean(0);   // 불리언 false
Object(3);    // new Number(3)와 동일한 결과로 숫자 3
```