# ORDER BY

특정컬럼 기준 정렬

- 오름차순
```sql
  SELECT * FROM tablename
    ...
    ORDER BY columnname1
```

- 오름차순
```sql
  SELECT * FROM tablename
    ...
    ORDER BY columnname1 ASC
```

- 내림차순
```sql
  SELECT * FROM tablename
    ...
    ORDER BY columnname1 DESC
```

- 다중정렬
```sql
  SELECT * FROM tablename
    ...
    ORDER BY columnname1 DESC, columnname2 ASC
```
