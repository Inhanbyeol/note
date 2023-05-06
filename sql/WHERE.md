# WHERE

[SELECT](sql/SELECT.md) 문법에 특정 조건을 부여할 수 있는 문법

- colname1에 '홍길동'이라는 데이터가 입력된 row 출력
```sql
  SELECT * FROM tablename
    WHERE colname1 = '홍길동'
```


- colname1에 '홍길동' colname2에 '30'이라는 데이터가 입력된 row 출력

```sql
  SELECT * FROM tablename
    WHERE colname1 = '홍길동' and colname2 = 30
```

- colname1에 '홍길동' 혹은 '김철수'라는 데이터가 입력된 row 출력

```sql
  SELECT * FROM tablename
    WHERE colname1 = '홍길동' or colname1 = '김철수'
```
