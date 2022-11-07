# for

### for

- '0'부터 'a'의 개체 수 만큼 반복 예시
```js

let a = [1,3,2,4,5,6,4,3]

for (i = 0; i < a.length; i++) { //초기식; 조건식; 증감식

  console.log(a[i]);

}

//1
//3
//2
//4
//5
//6
//4
//3
```

### for / in

- 0부터 a의 개체 수 만큼 반복 예시
```js

let a = [1,3,2,4,5,6,4,3]

for (var i in a) {

  console.log(a[i]);

}

//1
//3
//2
//4
//5
//6
//4
//3

```

- 변수 내부의 properties 접근
```js

let a = {
          name : '인한별',
          age : 29
        }

for (var i in a) {

  console.log(a[i]);

}

//인한별
//29
```
