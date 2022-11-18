# 함수 선언식과 함수 표현식, 차이와 장점

  ## 함수 선언식 (Function Declarations)
  - 일반적인 함수 선언 방식
```js
function funcDeclarations() {
    return 'enchovy';
}
 
funcDeclarations();
```


  ## 함수 표현식 (Function Expressions)
  - 자바스크립트 언어의 특징을 활용한 선언 방식
```js
let funcExpression = function () {
    return 'enchovy';
}
 
funcExpression();
```
   - ※ ES6에서 추가된 화살표 함수 방식을 정의할 수도 있다.
```js
let funcArrow = (x,y) => (x+y)
```

  ## 함수 선언식과 표현식의 차이
  ### 스코프와 호이스팅
  함수 선언문은 var와 같이 함수 스코프(function scope)를 가지고 let과 const 변수는 블록 스코프(block scope)를 갖는다. 또한, 함수 선언식은 코드가 실행되기 전에 로드되지만, 함수 표현식은 인터프리터가 해당 코드 줄에 도달할 때 로드된다. 함수 선언식은 호이스팅 되지만 함수 표현식은 호이스팅 되지 않으므로 정의된 범위에서 로컬 변수의 복사본을 유지할 수 있다.   
  
  - 함수 선언식은 블록문 밖에서 호출이 가능하다. 
```js
// 선언 전에 호출되도 정상 동작된다
// 1
console.log(enchovy());
function enchovy() {
    return 1;
}
```
  
  - 함수 표현식은 선언한 변수에 할당하는지에 따라 스코프가 달라진다.
```js
 // 로드되지 않아 error 발생
console.log(enchovy());
const enchovy = function() {
    return 1;
}
```

  ## 함수 표현식의 장점
  ‘함수 표현식이 호이스팅에 영향을 받지 않는다’는 특징 이외에도 함수 선언식보다 유용하게 쓰이는 경우는 클로져 사용과 인자 값으로 전달 시가 있다.   
