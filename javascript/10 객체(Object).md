# 객체(Object)

자바스크립트는 객체 기반의 스크립트 언어이며 자바스크립트를 이루고 있는 거의 모든 것이 객체이다.

원시 타입을 제외한 나머지 값들(함수, 배열, 정규식표현 등)은 모두 객체이다.

**자바스크립트의 객체는 키(key)와 값(value)으로 구성된 프로퍼티(property)들의 집합이다.**

프로퍼티 값으로 함수를 사용할 수도 있으며 프로퍼티 값이 함수일 경우, 일반 함수와 구분하기 위해 메소드라 부른다.

🔸 자바스크립트의 객체는 객체지향의 상속을 구현하기 위해 ‘프로토타입’이라고 불리는 객체의 프로퍼티와 메소드를 상속받을 수 있다. → 타 언어와 구별되는 중요한 개념!

### 프로퍼티(property)

---

프로퍼티는 프로퍼티 키(이름)과 프로퍼티 값으로 구성된다.

프로퍼티는 프로퍼티 키로 유일하게 식별할 수 있다. → 프로퍼티 기는 프로퍼티를 식별하기 위한 식별자다.

🔸 프로퍼티 키 : 빈 문자열을 포함하는 모든 문자열 또는 symbol 값

🔸 프로퍼티 값 : 모든 값

프로퍼티 키에 문자열이나 symbol 이외의 값을 지정하면 암묵적으로 타입 변환되어 문자열이 된다.

프로퍼티 키를 중복 선언하면 나중에 선언한 프로퍼티가 먼저 선언한 프로퍼티를 덮어쓴다.

배열과 달리 객체는 프로퍼티를 열거할 때 순서를 보장하지 않는다.

### 메소드(method)

---

프로퍼티 값이 함수일 경우, 일반 함수와 구분하기 위해 메소드라 부른다.

즉, 메소드는 객체에 제한되어 있는 함수를 의미한다.

## 객체 생성 방법

### 객체 리터럴

---

가장 일반적인 자바스크립트의 객체 생성 방식이다.

중괄호를 사용하여 객체를 생성하는 데 { } 내에 1개 이상의 프로퍼티를 기술하면 해당 프로퍼티가 추가된 객체를 생성할 수 있다.

{ } 내에 아무것도 기술하지 않으면 빈 객체가 생성된다.

```jsx
var person = {};
console.log(typeof person); // object
```

### Object 생성자 함수

---

new 연산자와 Object 생성자 함수를 호출하여 빈 객체를 생성할 수 있다.

생성자 함수란 new 키워드와 함께 객체를 생성하고 초기화하는 함수를 말한다.

생성자 함수를 통해 생성된 객체를 인스턴스(instance)라 한다.

일반 함수와 생성자 함수를 구분하기 위해 생성자 함수의 이름은 파스칼 케이스를 사용하는 것이 일반적이다.

```jsx
// 빈 객체의 생성
var person = new Object();

// 프로퍼티 추가
person.name = 'Lee';
person.gender = 'male';
person.sayHello = function () {
  console.log('Hi! My name is ' + this.name);
};

console.log(typeof person); // object
console.log(person); // {name: "Lee", gender: "male", sayHello: ƒ}

person.sayHello(); // Hi! My name is Lee
```

🔸 반드시 object 생성자 함수를 사용해 빈 객체를 생성해야 되는 것은 아니다. → 객체 리터럴을 사용하는 것이 더 간편

🔸 자바스크립트 엔진은 객체 리터럴로 객체를 생성하는 코드를 만나면 내부적으로 Object 생성자 함수를 사용하여 객체를 생성한다. → 개발자가 일부러 Object 생성자 함수를 사용해 객체를 생성할 일은 거의 없다.

### 생성자 함수

---

객체 리터럴 방식과 Object 생성자 함수 방식으로 객체를 생성하는 것은 프로퍼티 값만 다른 여러 개의 객체를 생성할 때 불편하다.

생성자 함수를 사용하면 마치 객체를 생성하기 위한 템플릿(클래스)처럼 사용하여 프로퍼티가 동일한 객체 여러 개를 간편하게 생성할 수 있다.

```jsx
// 생성자 함수
function Person(name, gender) {
  this.name = name;
  this.gender = gender;
  this.sayHello = function(){
    console.log('Hi! My name is ' + this.name);
  };
}

// 인스턴스의 생성
var person1 = new Person('Lee', 'male');
var person2 = new Person('Kim', 'female');

console.log('person1: ', typeof person1); //object
console.log('person2: ', typeof person2); //object
console.log('person1: ', person1); // [object Object]
console.log('person2: ', person2); // [object Object]

person1.sayHello(); // Hi! My name is Lee
person2.sayHello(); // Hi! My name is Kim
```

🔸 생성자 함수의 이름은 일반적으로 대문자로 시작한다.

🔸 프로퍼티 또는 메소드명 앞에 기술한 this는 생성자 함수가 생성한 인스턴스를 가리킨다.

🔸 this에 연결되어 있는 프로퍼티와 메소드는 public(외부에서 참고 가능)하다.

🔸 생성자 함수 내에서 선언된 일반 변수는 private(외부에서 참조 불가)하다. 즉, 생성자 함수 내부에서는 접근이 가능하나 외부에서 접근할 수 없다.

```jsx
function Person(name, gender) {
  var married = true;         // private
  this.name = name;           // public
  this.gender = gender;       // public
  this.sayHello = function(){ // public
    console.log('Hi! My name is ' + this.name);
  };
}

var person = new Person('Lee', 'male');

console.log(typeof person); // object
console.log(person); // Person { name: 'Lee', gender: 'male', sayHello: [Function] }

console.log(person.gender);  // 'male'
console.log(person.married); // undefined
```