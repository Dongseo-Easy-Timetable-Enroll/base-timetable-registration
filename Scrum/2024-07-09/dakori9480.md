#### 작성 : dakori9480

**작성 날짜 : 2024-07-09**

---

### 어제까지 무엇을 했는가?

- SQLD 책을 해결하기 위한 기본 세팅 완료
- SQLD 진행을 위한 다양한 예제 서칭

---

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

---

3. 모든 레코드 출력

```SQL
SELECT *
FROM ANIMAL_INS
ORDER BY ANIMAL_ID ASC;
```

---

4. 역순 정렬

```SQL
SELECT NAME, DATETIME
FROM ANIMAL_INS
ORDER BY ANIMAL_ID DESC;
```

---

5. 아픈 동물 찾기

```SQL
SELECT ANIMAL_ID, NAME
FROM ANIMAL_INS
WHERE INTAKE_CONDITION = 'Sick'
ORDER BY ANIMAL_ID ASC;
```

---

### 오늘 무엇을 계획하고 있는가?

- SQLD책 공부 시작
- 프로그래머스 문제해결 (SELECT 고난이도 문제 도전)

### 어떤 문제점이 있거나 도움이 필요한 것이 있는가?

- 치과 방문으로 인한 많은 시간을 할애하기 힘듦
