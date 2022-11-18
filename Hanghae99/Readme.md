# Javascript 이해하기

### 느슨한 타입(loosely typed)의 동적(dynamic)언어
Javascript는 느슨한 타입(loosely typed)의 동적(dynamic) 언어입니다.
Javascript의 변수는 어떤 특정 타입과 연결되지 않으며, 모든 타입의 값으로 할당 (및 재할당) 가능합니다.

```js
let foo = 42 // foo가 숫자
foo = 'bar' // foo가 이제 문자열
foo = true // foo가 이제 불리언
```

### JavaScript 형변환
함수와 연산자에 전달되는 값은 대부분 적절한 자료형으로 자동 변환됩니다. 이런 과정을 '형 변환(type conversion)'이라고 합니다.
자바스크립트는 **자동 형변환** 기능을 가졌는데, 가볍게 보면 매우 편리한 기능이지만 알고보면 버그를 만들기 매우 쉬운 위험한 문법으로 받아들여야 합니다.
추가로, 자동 형변환이 아닌, 형변환의 의도를 갖고 원하는 타입으로 변경할 수 있습니다.


- 자동 형변환 예시

  숫자 자료형을 가진 값에 자동 형변환이 적용되는 경우, 문자열로 변환이 가능하다고 여겨 '10' === '10' 처럼 동작한다고 이해하면 됩니다.
```js
let a = 10
let b = '10'

a == b // true
a === b // false
```

- 수동 형변환 예시
```js
parseInt(val)    //문자를 정수형 숫자로 변환해줌
parseFloat(val)     //문자를 실수형 숫자로 변환해줌
Nember(val)    //문자를 정수&실수형 숫자로 변환해줌
```
```js
let a = '999'
let b = '99.99'

  parseInt(a)    //숫자형 정수 999
  parseInt(b)    //숫자형 정수 99

  parseFloat(a)    //숫자형 실수 999
  parseFloat(b)    //숫자형 실수 99.99

  Number(a)    //숫자형 정수 999
  Number(b)    //숫자형 실수 99.99
```
      
```js
let a = "a999"    //문자형 a999
let b = "a99.99"    //문자형 a99.99

  parseInt(c)    //숫자형 NaN
  ParseInt(d)    //숫자형 NaN

  parseFloat(c)    //숫자형 NaN
  parseFloat(d)    //숫자형 NaN

  Number(c)    //숫자형 NaN
  Number(d)    //숫자형 NaN
```
         
```js
let a = "999a9"    //문자열 999a9
let b = "99.9a9"    //문자열 99.9a9

  parseInt(a)    //숫자형 999
  parseInt(b)    //숫자형 99

  parseFloat(a)    //숫자형 999
  parseFloat(b)    //숫자형 99.9

  Number(a)    //숫자형 NaN
  Number(b)    //숫자형 NaN
```
