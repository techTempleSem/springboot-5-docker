# docker로 db 세팅

mysql workbench와 docker 필요

docker을 실행한 상태여야 함

```yaml
version: "3"
services:
  db:
    image: mysql:8.0.26
    restart: always
    command:
      - --lower_case_table_names=1
      - --character-set-server=utf8mb4
      - --collation-server=utf8mb4_unicode_ci
    container_name: mysql
    ports:
      - "3306:3306"
    environment:
      - MYSQL_DATABASE=mydb
      - MYSQL_ROOT_PASSWORD=root1234!!
      - TX=Asia/Seoul
    volumes:
      - C:\TEMP\MYSQL:/var/lib/mysql
```

"3306:3306" : 앞이 로컬 포트, 뒤가 도커 포트

로컬의  C:\TEMP\MYSQL와 도커의 /var/lib/mysql을 연결