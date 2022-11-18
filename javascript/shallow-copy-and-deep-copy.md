# shallow copy and deep copy

## 얕은 복사(shallow copy)란?
```js
const obj1 = { a: 1, b: 2};
const obj2 = obj1;
console.log( obj1 === obj2 ); // true
```
  - 위의 예시처럼 객체를 직접 대입하는 경우 참조에 의한 할당이 이루어지므로 둘은 같은 데이터(주소)를 가지고 있다.
  - 이것이 얕은 복사이다.

```js
const obj1 = { a:1, b:2 };
const obj2 = obj1;
obj2.a = 100;
console.log( obj1.a ); // 100
```
  - 위 두 객체는 같은 데이터(주소)를 가지고 있고, 그래서 같은 주소를 참조하고 있다.
  - 때문에 obj2의 property를 수정하고, obj1를 출력해도 obj2 값과 동일하다.

## 깊은 복사(deep copy)란?
> 얇은 복사 처럼 주소를 복사해서 공유하는 것이 아니라, 아예 새로운 객체안 속성(property)만 복사 해서 사용할 수 없을까?

### 방법 1. …(spread) 연산자를 통한 복사 (과연 깊은 복사가 될까?)
```js
const obj1 = { a:1, b:2 };
const obj2 = { ...obj };
obj2.a = 100;
console.log( obj1 === obj2 ) // false
console.log( obj1.a ) // 1
```
  - `...(spread)` 연산자를 통해 `{ }`안에 `obj1`의 속성을 복사하여 `obj2`에 할당하였다.
  - 이제 `obj1`과 `obj2`는 다른 주소를 갖게되었다. `(그러나 딱, 1 depth 까지만)`

### 방법 2. Object.assign() 메소드를 통한 복사 (과연 깊은 복사가 될까?)
```js
const obj1 = { a:1, b:2 };
const obj2 = Object.assign({}, obj1);

obj2.a = 100;

console.log( obj1 === obj2 ) // false
console.log( obj1.a ) // 1
```

  - Object.assign() 메소드를 통해 첫 번째 인자로 빈 { } 객체를, 두 번째 인자로 obj1 넣고 obj2 에 할당하였다.
  - 이제 obj1과 obj2는 다른 주소를 갖게되었다. (그러나 딱, 1 depth 까지만)


## 주의, 깊은 복사의 함정
  ### MDN의 전개 구문
  > Spread 문법은 배열을 복사할 때 1 레벨 깊이에서 효과적으로 동작합니다. 그러므로, 다음 예제와 같이 다차원 배열을 복사하는것에는 적합하지 않을 수 있습니다. (Object.assign() 과 전개 구문이 동일합니다)

  - Object.assign() 메소드도 spread 연산자 둘 다 완벽한 Deep copy 되지 않는다.
  - 객체가 서로 다르다고 깊은 복사가 이루어진건 아니다.
  - 1 depth 까지는 확실하게 Deep copy.
  - 2 depth 이상이면 Shallow copy.

  ### …(spread) 연산자를 이용해 depth 2까지 복사하는 방법
```js
const obj1 = { a: { b:1, c:1 }, d: 2};
const obj2 = { ...obj1, a:{ ...obj1.a } };
obj1.a.b = 100;
console.log(obj1 === obj2) // false
console.log(obj2.a.b) // 1
```
