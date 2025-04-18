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
