# 함수(function)

자바스크립트 함수는 특정 작업을 수행하는 코드 블록이다.

함수는 여러 번 호출될 수 있으며, 호출될 때마다 동일한 작업을 수행한다.

코드의 재사용성을 높이고, 코드를 더 구조화하며, 유지보수에 용이하다.

**기본 문법**

```jsx
function 함수명(매개변수){
	실행 코드
	return 반환값;
}
```

### 함수 선언

---

function 키워드를 사용하여 함수의 이름과 함께 정의

호이스팅의 영향을 받음 → 어디서든 호출 가능

```jsx
function greet(){
	console.log("Hello World!");
}

greet();  // 함수 호출 -> Hello World! 출력
```

### 함수 표현식

---

변수를 사용하여 함수를 정의하는 방식

호이스팅의 영향을 받지 않음 →  함수가 정의된 이후에만 호출 가능

함수 표현식은 익명 함수 또는 기명 함수로 정의할 수 있다.

```jsx
const greet = funstion(){
	console.log("Hello World!");
}

greet(); // 함수 호출 -> Hello World! 출력
```

```jsx
// 기명 함수 표현식(named function expression)
var foo = function multiply(a, b) {
  return a * b;
};

// 익명 함수 표현식(anonymous function expression)
var bar = function(a, b) {
  return a * b;
};

console.log(foo(10, 5)); // 50
console.log(multiply(10, 5)); // Uncaught ReferenceError: multiply is not defined
```

### 선언과 표현식의 차이점

---

1. **호이스팅(Hoisting)**
    
    var 선언문이나 function 선언문 등 모든 선언문이 해당 Scope의 선두로 옮겨진 것처럼 동작하는 특성을 의미한다.
    
    🔸 함수 선언 : 호이스팅 됨 → 함수 코드의 어느 위치에서든 호출이 될 수 있음을 의미
    
    🔸 함수 표현식 : 호이스팅 되지 않음 → 함수가 정의된 이후에만 호출될 수 있음
    
2. **구문**
    
    🔸 함수 선언 : function 키워드와 함께 함수 이름을 명시하여 정의
    
    🔸 함수 표현식 : function 키워드를 사용하여 함수를 변수에 할당
    
3. **디버깅**
    
    🔸 함수 선언 : 함수 이름을 포함하므로 디버깅 시 호출 스택에서 함수 이름을 쉽게 확인 할 수 있음
    
    🔸 익명 함수 표현식 : 함수 이름이 없으므로 디버깅 시 호출 스택에서 함수 이름을 확인하기 어려움
    
4. **사용 용도**
    
    🔸 함수 선언 : 주로 독립적인 함수를 정의할 때 사용
    
    🔸 함수 표현식 : 콜백 함수나 일회성 함수를 정의할 때 유용
    

### 함수 호출 방법

---

자바스크립트에서 함수를 호출하는 기본적인 방법은 함수 이름 뒤에 괄호를 붙이는 것이다.

괄호 안에는 해당 함수가 필요로 하는 인자를 넣을 수 있다.

```jsx
function sayHello() {
  console.log("Hello, world!");
}

// 함수 호출
sayHello(); // 콘솔에 "Hello, world!" 출력
```

### 매개변수(parameter, 인자) VS 인수(argument)

---

🔸 **매개변수**

전달된 값을 받아들이는 변수를 의미 → 함수를 정의할 때 함수 선언식의 괄호 `()` 안에 쓰는 변수

함수 내에서 변수와 동일하게 메모리 공간을 확보하며 함수에 전달한 인수는 매개변수에 할당된다. 만약 인수를 전달하지 않으면 매개변수는 undefined로 초기화된다.

```jsx
function sum(a, b) {	// a, b는 매개변수(parameter)
  return a + b;
}
sum(10, 20);	// 10, 20은 인자(argument)
```

🔸 **인자**

어떤 함수가 호출될 때 전달되는 값, 정의된 변수를 의미

함수에서 매개변수를 적어둔 상태라면, 호출시 인자로 전달한 값을 매개변수를 통해 사용이 가능하다.

### call-by-value, call-by-reference

---

변수나 객체등이 함수의 인자(argument)로 들어와 매개변수(parameter)로 전달될 때 어떤 방식으로 전달될 지를 결정하는 방식이다.

원시타입(기본형) : 숫자, 문자열, 불리언, null, undefiend, symbol

객체형(참조형) : 객체, 배열, 함수, 날짜, 정규표현식

**🔸 call-by-value(값에 의한 호출, 값의 복사)**

원시타입(기본형) 인수는 call-by-value로 동작한다.

복사된 값을 인자로 넘겨서 매개변수로 전달한다.

이때 함수내에서 매개변수를 통해 값이 변경되어도 전달이 완료된 원시 타입 값은 변경되지 않는다.

```jsx
function foo(primitive) {
  primitive += 1;
  return primitive;
}

var x = 0;

console.log(foo(x)); // 1
console.log(x);      // 0
```

장점 : 복사하여 처리하기 때문에 안전하다. 원래의 값이 보존된다.

단점 : 복사를 하기 때문에 메모리 사용량이 늘어난다.

**🔸 call-by-reference(참조에 의한 호출, 주소의 복사)**

객체형(참조형) 인수는 call-by-reference로 동작한다.

실제 데이터가 존재하는 주소를 가리키는 주소값을 인자로 넘겨서 매개변수로 전달한다.

이때 함수 내에서 매개변수의 참조값이 이용하여 객체의 값을 변경했을 때 전달되어진 참조형 인수값도 같이 변경된다.

```jsx
function changeVal(primitive, obj) {
  primitive += 100;
  obj.name = 'Kim';
  obj.gender = 'female';
}

var num = 100;
var obj = {
  name: 'Lee',
  gender: 'male'
};

console.log(num); // 100
console.log(obj); // Object {name: 'Lee', gender: 'male'}

changeVal(num, obj);

console.log(num); // 100
console.log(obj); // Object {name: 'Kim', gender: 'female'}
```

장점 : 복사하지 않고 직접 참조를 하기에 빠르다.

단점 : 직접 참조를 하기에 원래 값이 영향을 받는다.(리스크)

### 반환값 return

---

🔸 return 키워드는 함수를 호출한 코드에게 값을 반환할 때 사용한다.

🔸 함수는 배열 등을 이용하여 한 번에 여러 개의 값을 리턴할 수 있다.

🔸 함수는 반환을 생략할 수 있다. → 이때 함수는 암묵적으로 undefined를 반환한다.

🔸 자바스크립트 해석기는 return 키워드를 만나면 함수의 실행을 중단한 후, 함수를 호출한 코드로 되돌아간다. 만일 return 키워드 이후에 다른 구문이 존재하면 그 구문은 실행되지 않는다.