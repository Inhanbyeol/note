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

  ## var, let, const의 차이
  let 변수와 const는 ES6 이후 스펙에서 새롭게 등장한 변수이다. 그래서 브라우저 배포용 코드같은 경우는 아직도 var변수만 사용되는 경우도 있다고 한다.   
     
  - 값 변경 가능 유무
  - 스코프 범위
  - 호이스팅 가능 유무
   
    ### 우선 순위
      - const → let → var


    ### 값 변경 가능 유무
      - `var`와 `let`을 값이 선언된 이후에도 값을 변경할 수 있지만, `const`는 생성할 때 선언된 초기값을 변경할 수 없습니다.

    ### 함수 스코프, 블록 스코프
      - `var`은 함수스코프를 가지지만, `let`과 `const` 변수는 블록 스코프를 가지게 됩니다.

    ### 호이스팅 가능 유무
      - `var`는 호이스팅이 가능하지만, `let`과 `const`는 호이스팅이 불가능합니다.

```js
let name = 'inhanbyeol'

if(name) {
  let name = 'parkjei'
  console.log("블록 안에서", name); // parkjei
};

console.log("블록 밖에서", name); // inhanbyeol
```

   이렇게 if문을 감싸고 있는 {블락} 이 변수를 사용할 수 있는 영역이 되어 변수가 구분되어 진다.  
   위와 같이 `let`을 쓰면 **if**안과 밖으로 스코프가 달라지지만 (블록 안과 밖의 스코프가 달라져서 변수 이름이 같아도 값이 대체되지 않아 같은 스코프에는 같은 이름 사용 불가하다), name을 `var`변수로 선언 했을 경우에는 **if** 안과 밖이 같은 스코프가 되어서 "Uncaught SyntaxError: Identifier 'name' has already been declared"오류가 뜨게됨
   
   
  ## function()의 원리
     
  ### 엔진이 함수를 실행하는 방법
     
  - 함수를 실행하기 위해서는 이름(식별자)이 필요합니다. 이름이 있어야 스코프에서 값을 참조할 수 있기 때문입니다.
  - 예를 들어 function foo(){}를 정의하면 foo(); 구문을 이용해 함수를 실행할 수 있습니다.

  ![image](https://user-images.githubusercontent.com/117622086/202642072-20351df3-5e94-43c3-9c00-c3374c9d927d.png)
  
  엔진이 함수 선언문을 만나면 식별자를 관리하는 특별한 집합(EnviromentRecord)에 함수의 이름을 식별자로 넣고 함수 객체를 생성하여 참조합니다. 그리고 함수 실행 구문 중 foo를 만나면 값을 스코프를 통해 가져옵니다. 그 다음 구문이 () 이므로 실행 가능하다면 실행합니다.   
     
  만약 스코프에서 식별자를 찾지 못했다면 참조 에러(ReferenceError)를 출력하고, 식별자는 찾았지만 실행할 수 없는 타입이라면 타입 에러(TypeError)를 출력합니다.   
  

```js
not(); // ReferenceError: not is not defined

var foo = 'some';
foo(); // TypeError: foo is not a function
```
   
  ### 익명함수를 선언하는 방법
  function(){} 구문은 이름 없는 “익명함수” 이므로 엔진이 스코프를 통해 값을 가져올 수 있는 방법이 없습니다. 따라서 이 문법을 실행하면 함수의 이름이 필요하다고 문법 오류를 출력합니다.
  - 이름 없는 함수를 선언할 수 있는 유릴한 경우는 함수를 값으로 사용(전달, 대입, 반환, 연산)할 때 입니다.

```js
var func = function(){console.log('ok');}() // ok
some(function(){console.log('ok');})() // ok
return function(){console.log('ok');}() // ok
(function(){console.log('ok');})(); // ok
+function(){console.log('ok');}() // ok
!function(){console.log('ok');}() // ok
```

  +function(){}은 함수 객체를 + 하려고 했으므로 결과로 NaN이 출력됩니다.  
  +function(){} // NaN   

  결국 +function(){}()은 익명 함수를 즉시 실행시키기 위해 엔진의 원리를 이용해 만든 편법입니다.   

  이 원리를 이용한 즉시 실행 함수 중 가장 대중적인 방식은 (function(){})()입니다. ()는 구문 평가를 하는데 평가된 결과가 함수이니 함수 객체를 만들고 이어서 () 구문으로 즉시 실행하는 방식입니다.   

  (function(){}) // function() 객체   
  (function(){})() // 즉시 실행   
  남이 읽을때 혼란스럽지 않아야 좋은 코드라고 할 수 있겠죠. 따라서 비대중적인 +function(){}() 보다 (function(){})() 사용하여 코드를 읽는 개발자가 즉시 실행하는 함수 임을 쉽게 알 수 있도록 하는편이 좋겠습니다.   
  
