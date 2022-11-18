# 스코프 체인(Scope Chain)

스코프는 함수의 중첩에 의해 계층적 구조를 가진다.   

변수를 참조할 때, 자바스크립트 엔진은 스코프 체인을 통해 변수를 참조하는 코드의 스코프에서 시작하여 상위 스코프로 이동하면서 선언된 변수를 검색한다.   

스코프 체인은 outerEnvironmentReference와 밀접한 관계를 가진다.   

- 스코프 체인은 실행 컨텍스트의 렉시컬 환경을 '단방향'으로 연결한 링크드 리스트
![image](https://user-images.githubusercontent.com/117622086/202654763-a394c4ac-6d4a-46a9-96d4-fc5a34ad3f5f.png)
   
     
# 변수 은닉화(variable shadowing)

여러 스코프에서 동일한 식별자를 선언한 경우, 무조건 스코프 체인 상에서 가장 먼저 검색된 식별자에만 접근이 가능하다.   
```js
(function s(){
let a = 'hi'
})() //a is not defined
```

즉, 직접적으로 변경되면 안되는 변수에 대한 접근을 막는것이다.   
```js
function hello(name) {
  let _name = name;
  return function () {
    console.log('Hello, ' + _name);
  };
}

let a = new hello('영서');
let b = new hello('아름');

a() //Hello, 영서
b() //Hello, 아름
```
이렇게 a와 b라는 클로저를 생성하면 함수 내부적으로 접근이 가능하다.
