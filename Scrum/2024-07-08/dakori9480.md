#### 작성 : dakori9480

**작성 날짜 : 2024-07-08**

---

### 어제까지 무엇을 했는가?

- DB개론 12 ~ 13장

  - 12장

    - 객체지향 데이터모델 : 객체지향 개념에 기반을 둔 데이터 모델

      - 객체 : 현실 개체를 추상적으로 표현한 것이며 객체 식별자로 접근
      - 속성 : 관계 데이터 모델의 속성과 같은 의미
      - 클래스 : 객체들을 그룹화 한것
      - 클래스 계층 : 운동선수는 상위클래스, 축구선수와 야구선수는 하위클래스가 됨

        <img src = https://github.com/Dongseo-Easy-Timetable-Enroll/base-timetable-registration/assets/160097394/fb349bf5-e92d-4d88-8e40-45142f3ec3ee>

      - 상속 : 운동클래스를 제외한 모든 클래스가 상위클래스로 부터 속성과 메서드를 상속받음

      ***

    - 분산 데이터베이스 시스템 : 네트워크로 데이터베이스를 분산시킴

      - 분산 데이터 독립성 : 데이터베이스가 분산되어 있음을 사용자가 인식하지 못해야 함

        1. 위치 투명성 : 데이터베이스의 논리적 이름으로 접근 가능
        2. 중복 투명성 : 데이터를 중복 저장해서 문제가 생겨도 사용 가능
        3. 단편화 투명성 : 릴레이션을 단편으로 나눠 용량과 속도의 향상
        4. 병행 투명성 : 분산 데이터베이스가 트랙잭션을 동시에 수행해도 일관성 유지
        5. 장애 투명성 : 특정 시스템에 문제가 발생해도 전체 시스템은 작업 수행 가능

        - 장점 : 신뢰성, 가용성, 지역자치성, 효율성, 확장성 지원
        - 단점 : 개발 및 관리 비용이 많이 소모

  - 13장
    - DIKW 계층 구조
      1. 데이터(DATA) : 관찰 및 측정하여 수집한 사실이나 값
      2. 정보(Information) : 데이터를 목적에 맞게 가공한 것
      3. 지식(Knowledge) : 규칙과 패턴을 통해 찾아낸 정보
      4. 지혜(Wisdon) : 지식에 통찰력을 더해 창의적인 아이디어 도출

---

## 프로그래머스 SQL 문제 - SELECT

1. 조건에 맞는 도서 리스트 출력하기

```SQL
SELECT BOOK_ID, TO_CHAR(PUBLISHED_DATE, 'YYYY-MM-DD') AS PUBLISHED_DATE
FROM BOOK
WHERE TO_CHAR(PUBLISHED_DATE, 'YYYY-MM-DD') LIKE '2021%' AND CATEGORY = '인문'
ORDER BY PUBLISHED_DATE ASC;

날짜는 LIKE를 사용할 수 없으므로 문자열로 치환하여 사용합시다!
```

---

2. 3월에 태어난 여성 회원 목록 출력하기

```SQL
SELECT MEMBER_ID, MEMBER_NAME, GENDER, TO_CHAR(DATE_OF_BIRTH, 'YYYY-MM-DD') AS DATE_OF_CHAR
FROM MEMBER_PROFILE
WHERE GENDER = 'W'
AND TO_CHAR(DATE_OF_BIRTH, 'YYYY-MM-DD') LIKE '%03%'
AND TLNO IS NOT NULL
ORDER BY MEMBER_ID ASC;

NULL 값을 연산하고 싶다면 IS NULL / IS NOT NULL을 사용해봅시다!
```

---

3. 흉부외과 또는 일반외과 의사 목록 출력

```SQL
SELECT DR_NAME, DR_ID, MCDP_CD, TO_CHAR(HIRE_YMD,'YYYY-MM-DD') AS HIRE_YMD
FROM DOCTOR
WHERE MCDP_CD IN ('CS', 'GS')
ORDER BY HIRE_YMD DESC, DR_NAME ASC;

WHERE 절에서 2개 이상의 값을 찾고 싶다면 IN 연산자를 사용해봅시다!
```

---

4. 과일로 만든 아이스크림 고르기

```SQL
SELECT FIRST_HALF.FLAVOR
FROM FIRST_HALF
JOIN ICECREAM_INFO ON ICECREAM_INFO.FLAVOR = FIRST_HALF.FLAVOR
WHERE TOTAL_ORDER > 3000 AND INGREDIENT_TYPE = 'fruit_based'
ORDER BY TOTAL_ORDER DESC;

JOIN 합칠 테이블명 ON 합칠 테이블의 같은 속성의 열 = 기존 테이블의 같은 속성의 열
JOIN은 자주 사용되니 익숙해져 봅시다!
```

---

5. 평균 일일 대여 요금 구하기

```SQL
SELECT ROUND(AVG(DAILY_FEE)) AS AVERAGE_FEE
FROM CAR_RENTAL_COMPANY_CAR
WHERE CAR_TYPE = 'SUV';

ROUND는 소수점을 제거해줍니다!
```

6. 재구매가 일어난 상품과 회원 리스트 구하기

```SQL
SELECT USER_ID, PRODUCT_ID
FROM ONLINE_SALE
GROUP BY USER_ID, PRODUCT_ID
HAVING COUNT(*) > 1
ORDER BY USER_ID ASC, PRODUCT_ID DESC;

GROUP BY는 그룹화 하고 HAVING은 그룹별로 계산 할 때 사용되므로 익숙해져 봅시다!
```

---

### 오늘 무엇을 계획하고 있는가?

- SQLD 책 훑어보기
- 프로그래머스 SQL 문제 풀어보기

### 어떤 문제점이 있거나 도움이 필요한 것이 있는가?
