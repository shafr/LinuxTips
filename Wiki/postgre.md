Docker-compose - print all statements with values for psql:

```
db:
  image: postgres:12
  ports:
    - "5432:5432"
  environment:
    - "POSTGRES_PASSWORD=Password"
  command: postgres -c log_statement=all
  
```
