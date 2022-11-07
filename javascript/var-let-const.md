# var, let, const

### 변수 선언 방식

- var (중복 변수선언을 진행하여도, 이전에 선언된 변수를 무시하고 새로 선언하는 방식으로, 다소 유동적)
```js
var a = 'test'

console.log(a) //test

var a = 'user'

console.log(a) //user
```

- let (중복 변수선언 불가하여 선언 시 오류 발생, 재할당 가능)
```js
let a = 'test'

console.log(a) //test

---
let a = 'user'
console.log(a) //error : Identifier 'a' has already been declared

---
a = 'user'
console.log(a) //user

```

- const (중복 변수선언 불가하여 선언 시 오류 발생, 재할당 불가)
```js
let a = 'test'

console.log(a) //test

---
let a = 'user'
console.log(a) //error : Identifier 'a' has already been declared

---
a = 'user'
console.log(a) //Assignment to constant variable

```
