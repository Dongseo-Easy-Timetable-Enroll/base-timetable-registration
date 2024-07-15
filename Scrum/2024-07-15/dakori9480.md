#### 작성 : dakori9480

**작성 날짜 : 2024-07-15**

---

### 어제까지 무엇을 했는가?

- SQLD 6장

  - 일반집합연산자

    1. UNION : 합집합을 하는 연산
    2. UNION ALL : 교집합의 중복을 제거하지 않는 UNION
    3. INTERSECT : 교집합을 하는 연산
    4. DIFFERENCE : 차집합을 하는 연산 (ORACLE에선 MINUS로 구현)
    5. CROSS JOIN : JOIN 조건이 없는 모든 데이터의 조합

  - 순수관계연산자
    1. WHERE : 행들에 대한 부분집합
    2. PROJECT : 열들에 대한 부분집합
    3. JOIN : WHERE에 JOIN 조건을 구현
       1. INNER JOIN : 동일한 값이 있는 행만 반환
       2. NATURAL JOIN : 동일한 이름을 갖는 칼럼에 대해 INNER JOIN을 수행
       3. USING : NATURAL JOIN에서 원하는 칼럼만 INNER JOIN할 수 있음
       4. ON : 칼럼명이 달라도 JOIN을 사용할 수 있음
       5. CROSS JOIN : 테이블간 JOIN 조건이 없는 경우 모든 데이터의 조합
       6. OUTER JOIN : 동일한 값이 없는 행도 포함시킬 때 사용

- 자바 스프링 인프런 2/6 시청

### 오늘 무엇을 계획하고 있는가?

- SQLD 7장 정리
- 프로젝트에 사용할 데이터 테이블 생성하기
- 인프런 강의 1개 시청

### 어떤 문제점이 있거나 도움이 필요한 것이 있는가?
