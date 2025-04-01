---
title: "SQL Injection - Classic WHERE Clause"
date: 2025-04-01 10:00:00 +0900
tags: [PortSwigger, Web Security, SQLi]
categories: [SQL Injection]
---

## 💡 문제 설명

PortSwigger Web Security Academy의 SQL Injection 문제입니다.  
WHERE 절에서 인젝션을 유발하여 인증을 우회하는 방식입니다.

## 🔍 요청 / Burp 분석

```http
GET /product?category=Gifts'-- HTTP/1.1
```
🧨 공격 방식
' OR 1=1-- 를 주입하면 조건이 항상 참이 되어 모든 결과 반환

로그인, 상품 조회 등 우회 가능

✅ 해결 방법
Burp에서 요청 캡처

파라미터에 ' OR 1=1-- 삽입

응답 확인 → 성공 여부 판단

🧾 마무리
SQL Injection의 가장 기초적인 형태를 실습하며,
필터 우회와 쿼리 구조를 이해하는 기초를 다졌습니다.


---

### 🔹 3. 저장 & 커밋  
GitHub 웹에서 저장 → 몇 초 기다리면 블로그에 포스트가 나타날 거야!  
📎 블로그 주소: [https://yamewrong.github.io](https://yamewrong.github.io)

---

## ✨ 다음에 할 수 있는 것들

| 기능 | 설명 |
|------|------|
| 📸 이미지 첨부 | Burp 스크린샷 등을 `/assets/img/`에 업로드하고 마크다운으로 삽입 |
| 🗂 카테고리 정리 | XSS, SQLi 등 카테고리별로 포스트 분류 |
| 🔖 태그 기능 | `tags:`를 활용한 키워드 검색 기능 |
| 📄 About 페이지 | 너 자신 소개하는 페이지 (`about.md`) 생성 |
| 🌙 다크모드 커스터마이징 | Chirpy 기본 지원, 색상 바꾸고 싶으면 알려줘!

---

💬 첫 포스트 작성 완료되면 알려줘!  
다음으로 자동 체크리스트(GitHub 블로그 내 진행 상황 표시) 만드는 것도 바로 도와줄게 😎
