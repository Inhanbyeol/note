# 불변 객체를 만드는 방법

- 불변 객체란 변하지 않는 객체이다.
- 이미 할당된 객체가 변하지 않는다는 뜻이다.

### const

  - ES6문법부터 let과 const를 지원한다.
  - const 키워드는 변수를 상수로 선언할 수 있다.
  - 일반적으로 상수로 선언된 변수는 값을 바꾸지 못한다.

```js
const test = {};
test.name = "beom";

console.log(test);  // {"beom"}
```

  - ES6에서의 const는 할당된 값이 상수가 되는 것이 아닌 바인딩된 값이 상수가 되는, 즉 test변수가 상수가 되기 때문에 const 키워드로 선언된 test변수에는 객체 재할당은 불가능하지만 객체의 속성은 변경 가능하다.
  - 재할당이 불가능 한 이유는 변수와 값(객체) 사이의 바인딩 자체가 변경이 되기 때문에 상수인 test변수는 재할당이 불가능한 것이고
  - 객체의 속성이 변경가능 한 이유는 실제 객체가 변경은 되지만 ( {} -> name : "beom" ) 객체와 변수(test)사이의 바인딩은 변경이 되지 않기 때문에 객체의 속성은 변경가능한 것이다.
  - 때문에 비록 재할당은 불가능하지만 객체의 속성을 변경함으로 인해 변수에 바인딩된 객체의 내용까지 변경이 되기 때문에 불변객체라고 하기는 힘들다.
  
  
### Object.freeze()
  - Object.freeze() 메소드는 "객체를 동결하기 위한 메소드" 라고한다.
```js
let test = {
  name : 'beom'
}

Object.freeze(test);

test.name = 'Jung';
console.log(test) // {name: 'beom'}
```

- test 변수에 key value를 가진 객체를 바인딩 후 Object.freeze(test)를 사용해 바인딩된 변수를 동결 객체로 만들었다.
- 때문에 test 객체는 객체의 속성을 변경하는 시도는 불가능하다.
- Object.freeze()는 동결된 객체를 반환하지만 객체의 재할당은 가능하다.

```js
test = {
    age : 15
};
console.log(test); // {age: 15}
```

  - 위와 같이 객체의 재할당은 가능하다. 때문에 Object.freeze()도 불변 객체라고 할 수는 없을 것 같다.   
  
  *결국 불변 객체를 만들기 위해서는 const와 Object.freeze()를 조합하여 만들 수 있다.   
  (const의 재할당불가 + Object.freeze()의 객체속성 변경불가)   
  
  ```js
  const test = {
    'name' : 'jung'
};

Object.freeze(test);
  ```
  - const키워드로 바인딩 된 변수를 상수화 시킨 다음, Object.freeze()로 해당 변수를 동결 객체를 만들면 객체의 재할당과 객체의 속성 둘 다 변경불가능한 불변 객체가 된다.
