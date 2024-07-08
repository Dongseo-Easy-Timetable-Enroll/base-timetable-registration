#### 작성 : dakori9480

**작성 날짜 : 2024-07-09**

---

### 어제까지 무엇을 했는가?

- SQLD 책을 해결하기 위한 기본 세팅 완료
- 프로그래머스 문제 해결 : SELECT

1. 강원도에 위치한 생성공장 목록 출력

```SQL
SELECT FACTORY_ID, FACTORY_NAME, ADDRESS
FROM FOOD_FACTORY
WHERE ADDRESS LIKE '강원도%'
ORDER BY FACTORY_ID ASC;
```

---

2. 12세 이하인 여자 환자 목록 출력

```SQL
SELECT PT_NAME, PT_NO, GEND_CD, AGE, NVL(TLNO,'NONE') AS TLNO
FROM PATIENT
WHERE GEND_CD = 'W' AND AGE < 13
ORDER BY AGE DESC, PT_NAME ASC;

NVL을 사용하여 아무것도 없을 때 NULL 대신 출력할 수 있는 방법이므로 확인해둡시다!
```

### 오늘 무엇을 계획하고 있는가?

### 어떤 문제점이 있거나 도움이 필요한 것이 있는가?
