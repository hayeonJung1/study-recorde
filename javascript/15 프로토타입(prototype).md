# 프로토타입(prototype)

🔸 자바스크립트는 프로토타입 기반 객체지향 프로그래밍 언어이다.

🔸 자바스크립트의 동작 원리를 이해하기 위해서는 프로토타입의 개념을 잘 이해하고 있어야 한다.

🔸 프로토타입 기반 객체지향 언어는 클래스 없이도 객체를 생성할 수 있다.

### 프로토타입

---

프로토타입은 객체가 다른 객체로부터 속성과 메소드를 상속받을 수 있게 해주는 매커니즘이다. 즉 객체가 상속받는 다른 객체를 의미한다.

객체는 자신에게 없는 프로퍼티나 메소드를 찾을 때 프로토타입 체인을 따라 올라가며 찾는다.

```jsx
function Person(name) {
  this.name = name;
}

// Person의 prototype에 greet 메서드를 추가
Person.prototype.greet = function () {
  console.log(`Hi, I'm ${this.name}`);
};

// 인스턴스 생성
const alice = new Person("Alice");

// alice에는 greet가 없지만, 프로토타입에서 찾음
alice.greet(); // 출력: Hi, I'm Alice

```

### 프로토타입 체인

---

프로토타입 체인은 상속을 따라 연결된 객체의 연결 구조이다.

객체는 내부적으로 `[[Prototype]]` 이라는 숨겨진 참조를 가지고 있다.

ES6이후엔 `Object.getPrototypeOf(obj)`로 확인 가능하고, `_proto_` 속성으로 볼 수 있다.

```jsx
console.log(alice.__proto__ === Person.prototype); // true
console.log(Person.prototype.__proto__ === Object.prototype); // true
```

즉 프로토타입 체인을 따라 올라가면서 속성을 찾는 구조이다.

alice → Person.prototype → Object.prototype → null

🔸 사용 이유

1. 공통 메서드 공유
    
    → 객체마다 같은 함수를 복사하지 않고, 메모리 절약 가능
    
2. 상속 구조 구현 가능
    
    → 부모-자식 구조로 기능 확장 기능