### JavaScript 형 변환
함수와 연산자에 전달되는 값은 대부분 적절한 자료형으로 자동 변환됩니다. 이런 과정을 '형 변환(type conversion)'이라고 합니다.
자바스크립트는 **자동 형변환** 기능을 가졌는데, 가볍게 보면 매우 편리한 기능이지만 알고보면 버그를 만들기 매우 쉬운 위험한 문법으로 받아들여야 합니다.
추가로, 자동 형변환이 아닌, 형변환의 의도를 갖고 원하는 타입으로 변경할 수 있습니다.

- 자동 형 변환 예시
```js
let a = 10
let b = '10'

a == b // true
a === b // false
```
         
- 명시적 형 변환 예시
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
```js
var trans = 100; //Number

Object(trans); //100
console.log(typeof trans); //Number
toString(trans); //”100"
console.log(typeof trans); //String
Boolean(trans); //true
console.log(typeof trans); //Bolean
```

- 산술연산자
  더하기(+) 연산자는 숫자보다 문자열이 우선시 되기 때문에, 숫자형이 문자형을 만나면 문자형으로 변환하여 연산된다.
```js
number + number // number
number + string // string
string + string // string
string + boolean // string
number + boolean // number
50 + 50; //100
100 + “점”; //”100점”
“100” + “점”; //”100점”
“10” + false; //”100"
99 + true; //100
```
  다른 연산자(- * / %)는 숫자형이 문자형보다 우선시되기 때문에 더하기와 같은 문자형으로의 변환이 일어나지 않는다.

```js
/다른 연산자(-,*,/,%)
string * number // number
string * string // number
number * number // number
string * boolean //number
number * boolean //number
“2” * false; //0
2 * true; //2
```
