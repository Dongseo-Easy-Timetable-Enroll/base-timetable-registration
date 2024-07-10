#### 작성 : dakori9480

**작성 날짜 : 2024-07-10**

---

### 어제까지 무엇을 했는가?

- SQLD 3장 공부
- 3장

  - 모델링 : 현실세계를 단순화시켜 표현

    - 추상화 : 일정한 형식에 맞게 표현
    - 단순화 : 규약을 지켜 언어로 표현
    - 명확화 : 여러명이 이해하기 쉽게 표현

  - 데이터 모델링 : 현실세계의 비즈니스를 IT시스템으로 구축
  - 모델링 순서

    1. 개념적 데이터 모델링 : 구현하는 대상의 포괄적 수준의 데이터 모델링 - E-R 다이어그램
    2. 논리적 데이터 모델링 : 비즈니스를 위한 각종 스키마를 작성하는 단계 - 정규화 단계
    3. 물리적 데이터 모델링 : DDL을 작성하여 테이블을 생성하는 과정=

  - 데이터베이스 3단계 구조

    - 외부 단계 : 외부 스키마 : 각자의 사용자가 보는 스키마
    - 개념적 단계 : 개념 스키마 : 모든 사용자의 관점을 통합한 전체 스키마
    - 내부적 단계 : 내부 스키마 : DB가 물리적으로 저장된 형식을 표현한 스키마

    - 논리적 데이터 독립성(외부/개념 사상) : 개념 스키마가 변경되어도 외부 스키마는 영향을 받지않음
    - 물리적 데이터 독립성(개념/내부 사상) : 내부 스키마가 변경되어도 외부/개념 스키마는 영향을 받지않음

---

1. 서울에 위치한 식당 목록 출력 (난이도 4/5)

```SQL
SELECT A.REST_ID, A.REST_NAME, A.FOOD_TYPE, A.FAVORITES, A.ADDRESS,
       ROUND(AVG(B.REVIEW_SCORE), 2) AS SCORE
FROM REST_INFO A
JOIN REST_REVIEW B ON A.REST_ID = B.REST_ID
WHERE A.ADDRESS LIKE '서울%'
GROUP BY A.REST_ID, A.REST_NAME, A.FOOD_TYPE, A.FAVORITES, A.ADDRESS
ORDER BY SCORE DESC, A.FAVORITES DESC;

AVG를 사용하려면 GROUP BY는 꼭 사용해야합니다!
소수점 단위를 조절하고 싶다면 ROUND를 사용해 소수점을 조절해봅시다!
```

---

2. 오프라인/온라인 판매 데이터 통합하기 (난이도 4/5)

```SQL
SELECT TO_CHAR(SALES_DATE,'YYYY-MM-DD') AS SALES_DATE, PRODUCT_ID, USER_ID, SALES_AMOUNT
FROM ONLINE_SALE
WHERE SALES_DATE BETWEEN TO_DATE('2022-03-01','YYYY-MM-DD') AND TO_DATE('2022-03-31','YYYY-MM-DD')
UNION
SELECT TO_CHAR(SALES_DATE,'YYYY-MM-DD') AS SALES_DATE,PRODUCT_ID,  NULL AS USER_ID, SALES_AMOUNT --오프라인은 USER_ID가 없음!
FROM OFFLINE_SALE
WHERE SALES_DATE  BETWEEN TO_DATE('2022-03-01','YYYY-MM-DD') AND TO_DATE('2022-03-31','YYYY-MM-DD')
ORDER BY SALES_DATE ASC;

UNION을 사용하면 두개의 테이블의 데이터를 결합할 수 있습니다
각 열의 개수와 데이터 타입이 일치하고 정렬은 마지막에만 가능합니다
이번에는 날짜 조회를 BETWEEN을 사용해보았습니다
```

### 오늘 무엇을 계획하고 있는가?

- SQLD 4장
- Django 복습
- 시간이 남는다면 프로그래머스 연산부분 (SUM,MAX,MIN) 풀어보기

### 어떤 문제점이 있거나 도움이 필요한 것이 있는가?
