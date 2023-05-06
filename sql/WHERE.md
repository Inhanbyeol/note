# WHERE

[SELECT](sql/SELECT.md) 문법에 특정 조건을 부여할 수 있는 문법

- colname1에 '홍길동'이라는 데이터가 입력된 row 출력
```sql
  SELECT * FROM tablename
    WHERE colname1 = '홍길동'
```

### AND
- colname1에 '홍길동' colname2에 '30'이라는 데이터가 입력된 row 출력

```sql
  SELECT * FROM tablename
    WHERE colname1 = '홍길동' AND colname2 = 30
```

### OR
- colname1에 '홍길동' 혹은 '김철수'라는 데이터가 입력된 row 출력

```sql
  SELECT * FROM tablename
    WHERE colname1 = '홍길동' OR colname1 = '김철수'
```


### LIKE
- colname1에 '홍'으로 시작하는 데이터가 입력된 row 출력

```sql
  SELECT * FROM tablename
    WHERE colname1 LIKE '홍%'
```

- colname1에 '길'이라는 문자를 포함한 데이터가 입력된 row 출력

```sql
  SELECT * FROM tablename
    WHERE colname1 LIKE '%길%'
```

- colname1에 '동'으로 끝나는 데이터가 입력된 row 출력

```sql
  SELECT * FROM tablename
    WHERE colname1 LIKE '%동'
```

- colname1에 '홍'으로 시작하는 n자리(_기호 개수) 문자열 데이터가 입력된 row 출력

```sql
  SELECT * FROM tablename
    WHERE colname1 LIKE '홍__'
```

### NOT LIKE

- colname1에 '홍'으로 시작하지 않는 데이터가 입력된 row 출력

```sql
  SELECT * FROM tablename
    WHERE colname1 NOT LIKE '홍%'
```
