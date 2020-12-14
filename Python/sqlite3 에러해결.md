```cur.execute("INSERT INTO table_name (word) VALUES (?);", (word))```

위 쿼리를 실행하려는데 아래와 같은 에러가 떴다.

sqlite3.ProgrammingError: Incorrect number of bindings supplied. The current statement uses 1, and there are 2 supplied.

```cur.execute("INSERT INTO table_name (word) VALUES (?);", (word,))```

뒤에 콤마 붙여주니 해결됐다.
