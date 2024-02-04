![semo](https://private-user-images.githubusercontent.com/50188319/281732629-41a23c0d-8be3-4ea8-be22-6f1c8d328a1b.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjIwOTYsIm5iZiI6MTcwNzAyMTc5NiwicGF0aCI6Ii81MDE4ODMxOS8yODE3MzI2MjktNDFhMjNjMGQtOGJlMy00ZWE4LWJlMjItNmYxYzhkMzI4YTFiLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NDMxNlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTEwNTc4YjUzZWExYmE3NTczYmNhNDUyNzUwMGU5MzU5ZGEyMTdiNzIzNWJkNjFjZWJjM2Q4NmU2NWEyMzcxN2MmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.cCQBeRB5mTT6YXzx173XTCeeBCVAruv8qJVv1yLG46o)

<br>

# 프로젝트 개요

최근 코로나19가 종식되고 모임이 활성화됨에 따라 사용자들이 더 쉽게 모임을 생성 및 참여할 수 있게 도와주고자 함. 회원 가입 및 로그인, 프로필, 번개 모임(순간적인 모임) 및 동호회(지속적인 모임) 생성 및 참여, 채팅방, 번개 게시판, 동호회 게시판 등의 기능을 구현하여 사용자들이 효율적으로 모임을 생성 및 운영하고 참여할 수 있는 환경을 제공하는 것을 목표로 함. 또한 매너등급 시스템, 호스트의 초대를 통한 참여 기능과 피드백 기능을 통해 모임이 파투 날 확률을 줄이고 사용자에게 깨끗한 모임 환경을 제공.

---

<br>

# 시스템 설계

## 1.기능 설명
![image](https://github.com/focandlol/gathering/assets/50188319/508c3ba4-bc03-4bb9-bde1-9457a2d71899)

⚫ 회원가입 : 카카오 주소 찾기 Api를 활용한 주소입력 구현, java mail sender와 ajax를 활용한 이메일 인증 구현

---

⚫ 번개게시판 : 호스트가 글을 작성하면 댓글을 통해 가입 신청이 가능함. 호스트는 댓글 작성자의 프로필에서 매너등급을 확인한 후 모임에 초대.
   
   ---피드백 : 모임 종료 후 피드백을 통한 불건전한 참가자 신고 후 관리자가 확인 후 피신고자 매너 등급 하락.
   
---
⚫ 동호회게시판 : 효율적인 동호회 관리를 위한 게시판. 회원 관리, 공지 사항 작성, 동호회 앨범 서비스를 제공.
   
   ---앨범 : querydsl과 ajax을 활용한 No-offset 방식의 무한스크롤 앨범 페이지 구현.
   
---
⚫ 채팅방 : Spring websocket과 socketjs를 활용해서 모임 단위의 실시간 채팅방 구현.

---
⚫ 관리자 : 신고사항 처리, 문의 사항 처리. 회원 관리 구현.

---
⚫ 모바일 웹 : Media Query를 활용해 기기별 화면 크기에 따른 구성 요소들의 재배치 구현.

---
<br><br>

## 2.개발 환경, 도구 및 언어
![프로젝트 아키텍처](https://private-user-images.githubusercontent.com/50188319/281726710-7fa31809-ec33-490f-8cc7-2c3a720b929b.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjI0MzIsIm5iZiI6MTcwNzAyMjEzMiwicGF0aCI6Ii81MDE4ODMxOS8yODE3MjY3MTAtN2ZhMzE4MDktZWMzMy00OTBmLThjYzctMmMzYTcyMGI5MjliLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NDg1MlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTQ0YjUxYTY5MjJiNjhmMzJiMmE4YjJjYTZmZDJjZjRjZDBjYmQyOTMzODNiNTUzZjk1MTBjM2YwOTE0YzljNmImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.pqz8mEbzb9Shcf5X93njD8owsCQ0tJyFNCtBP9i59jo)

<br><br>

## 3.기능 설계 및 진척사항


### 3-1. 메인 페이지
![메인](https://private-user-images.githubusercontent.com/50188319/281681476-d5e1dfdd-d486-40f2-9d82-1a6ee0553f92.PNG?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjI1NDMsIm5iZiI6MTcwNzAyMjI0MywicGF0aCI6Ii81MDE4ODMxOS8yODE2ODE0NzYtZDVlMWRmZGQtZDQ4Ni00MGYyLTlkODItMWE2ZWUwNTUzZjkyLlBORz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NTA0M1omWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTk0ZTE3NzUzYTNiMGVkYjkxZWRmYjFmNGI5MzUyZGY3MTk0MTdiNWZiMDdlYzYyZWUzZTVlNTkyZmQ3MDliMmUmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.XxDIODnXbnIbL3H7SvvZogMSTEay_r41f_pj3Tru_Vo)

### 3-2. 번개 게시판
![번1](https://private-user-images.githubusercontent.com/50188319/281681642-a9eb03cc-4826-49dc-99e5-0c5b02377daa.PNG?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjI1MTAsIm5iZiI6MTcwNzAyMjIxMCwicGF0aCI6Ii81MDE4ODMxOS8yODE2ODE2NDItYTllYjAzY2MtNDgyNi00OWRjLTk5ZTUtMGM1YjAyMzc3ZGFhLlBORz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NTAxMFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTNmNDA2Y2U2NmQzZTVmNWFmYTBjNzVhODc2OTM5NDQ3ZjMxZjM4MDEwOWJhY2NmNmM3Y2VjY2RjOTg3MTkxNWImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.HCpJ0vi-Jdrmoydw2aFtBDRDRlUZ5UD7K1XMqtW6JHs)
![번개](https://private-user-images.githubusercontent.com/50188319/281680309-9606e337-7117-421a-86b4-4a858731b905.PNG?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjI1MjksIm5iZiI6MTcwNzAyMjIyOSwicGF0aCI6Ii81MDE4ODMxOS8yODE2ODAzMDktOTYwNmUzMzctNzExNy00MjFhLTg2YjQtNGE4NTg3MzFiOTA1LlBORz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NTAyOVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTk2NDQ2MDQ0ZGJiMTI4NGRmM2E0NDlhYmZlMDI1MjlmODA0MDk5ZjY5ZWE5MWNmNjVlYTViMTA4NGM0NjIxY2MmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.mUOFBPDTwNf1o5ljRPzXoy5gsuzNiDp4DzPRtRgpNUs)

### 3-3. 동호회 게시판
 ![동호회](https://private-user-images.githubusercontent.com/50188319/281680516-506be925-a811-43bb-99b5-600887d6d8cf.PNG?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjI1NjEsIm5iZiI6MTcwNzAyMjI2MSwicGF0aCI6Ii81MDE4ODMxOS8yODE2ODA1MTYtNTA2YmU5MjUtYTgxMS00M2JiLTk5YjUtNjAwODg3ZDZkOGNmLlBORz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NTEwMVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTc3OTI4ZWQ1MzM1NWZlNDhiYzI1YzU4MmNiZmY4MGFhNzQwYzIxMDAzYjA3ODczNDM3MjQwZTFjZDk2MjUwZDAmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.yIHhauvJfJJd6eDxlJwdV37muSccRJf1ArMr207DoDc)

 ### 3-4. 관리자 페이지
 ![구성3](https://private-user-images.githubusercontent.com/50188319/281679503-764dc9a4-fbb3-4b7f-a3c7-790b6d0c372f.PNG?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjI1ODUsIm5iZiI6MTcwNzAyMjI4NSwicGF0aCI6Ii81MDE4ODMxOS8yODE2Nzk1MDMtNzY0ZGM5YTQtZmJiMy00YjdmLWEzYzctNzkwYjZkMGMzNzJmLlBORz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NTEyNVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWRjNTliNTNkZTY0MGI4OTRkNGY5M2M2YmZmNTgwYjFmZTU1ZTQzMzIzYTJjOTdiMzQzOTE1MGQ4YzZiNjUxMDcmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.6KgCxW2mNyQqZchXkEuW0SwaOUEBObK_AqDtc-zKXUo)

<br><br>

### 진척 사항 
![진척](https://github.com/focandlol/gathering/assets/50188319/27779099-36bc-4e22-b70c-20d30ccc5207)

## 4.ERD


 ![erd](https://private-user-images.githubusercontent.com/50188319/281728312-593d4fce-3d18-46c8-bb83-4363a1f1403b.PNG?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjI2MjcsIm5iZiI6MTcwNzAyMjMyNywicGF0aCI6Ii81MDE4ODMxOS8yODE3MjgzMTItNTkzZDRmY2UtM2QxOC00NmM4LWJiODMtNDM2M2ExZjE0MDNiLlBORz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NTIwN1omWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTEzMjJlNjhkMGVjZDllNjZlNjkwNzMyOWIzYjdhN2QzZDFkNzMyMjM0NmE2YjVmZGUwODg0NWQ4YTc0YjZlYWMmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.qZX9H6WUj_V0KmMh8BEjs_oAZDbDEpi8XTrFhO4mSd8)

<br>

---

<br>

# Overview

<br>

### 1.메인 페이지


 ![인덱스](https://private-user-images.githubusercontent.com/50188319/281697323-1e1f6c1c-31b7-4622-8a37-3bf977010f1f.PNG?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjI2NzgsIm5iZiI6MTcwNzAyMjM3OCwicGF0aCI6Ii81MDE4ODMxOS8yODE2OTczMjMtMWUxZjZjMWMtMzFiNy00NjIyLThhMzctM2JmOTc3MDEwZjFmLlBORz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NTI1OFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWMzZjA4MzNmYTgxNDYyNDg3NGFjYWI2ZmZlYzdiM2M5Y2YyMmNmNGUzOTI3Yzc0NjY4MDJmZTE5NmFiMWFhZjImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.oY88EJD8epNfsemI2Cve7OEJIi7pXybF6MoM4g_lvsM)

<br>

### 2.회원가입 페이지


![회가](https://private-user-images.githubusercontent.com/50188319/281699920-b1925fe2-53bc-4267-be82-100adb90e64a.PNG?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjI3MDQsIm5iZiI6MTcwNzAyMjQwNCwicGF0aCI6Ii81MDE4ODMxOS8yODE2OTk5MjAtYjE5MjVmZTItNTNiYy00MjY3LWJlODItMTAwYWRiOTBlNjRhLlBORz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NTMyNFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTk3MGQ1YmE2NzNmYTM3ODFhM2U1ZWFmOTI1YjYxOTIxMjMwMDZhNTgwOGFiNDkxMTdmNzE2ZjhlMDVmZGFhMGUmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.IcJibr9wmn2s1IZBwksG91ynQmFKb_QMiEFZhxjM5vA)
![gmail](https://private-user-images.githubusercontent.com/50188319/281699293-7065ca27-7670-448b-87ef-4340195bc101.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjI3MzcsIm5iZiI6MTcwNzAyMjQzNywicGF0aCI6Ii81MDE4ODMxOS8yODE2OTkyOTMtNzA2NWNhMjctNzY3MC00NDhiLTg3ZWYtNDM0MDE5NWJjMTAxLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NTM1N1omWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTRjMDA5N2Y2NDNiODUxOGZkNjE2Y2FkYTM2ZjcwNjY0ZDNkN2MyNTE1NjY3OGMzOTdhZDgxMDJkZWYyYzc3OWUmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.cq0iYSbJ4y00iT6OZGazCyvXtlJIbTpm5Na7PkTONcA)

<br>

### 3.프로필 페이지


![프로필](https://private-user-images.githubusercontent.com/50188319/281703336-eb1637fe-1392-4590-b501-76b34191e8f0.PNG?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjI3NzMsIm5iZiI6MTcwNzAyMjQ3MywicGF0aCI6Ii81MDE4ODMxOS8yODE3MDMzMzYtZWIxNjM3ZmUtMTM5Mi00NTkwLWI1MDEtNzZiMzQxOTFlOGYwLlBORz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NTQzM1omWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTkyNDY2MTlkMWEwOTg1YzNmMjc1YWEyMDI5MjNjM2E5OWVhNDM3MDJhMWMwYjBiNzY1MWEwNzlhOTQ3YmU3ZjYmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.VZaS5bzOa6p8CiRVrF1Q-NrhW86Gw5m0pG5S6HRZBZw)

<br>

### 4.번개 게시판


![번개 게시판](https://private-user-images.githubusercontent.com/50188319/281703741-4ef8c0af-3dcf-4aba-a313-0984044ca04a.PNG?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjI3OTUsIm5iZiI6MTcwNzAyMjQ5NSwicGF0aCI6Ii81MDE4ODMxOS8yODE3MDM3NDEtNGVmOGMwYWYtM2RjZi00YWJhLWEzMTMtMDk4NDA0NGNhMDRhLlBORz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NTQ1NVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWZlNmMzYjY1ZjNmNjZkYWUxM2JkNzY2MDhmZDYyNDUyYjhiNjFiYzYxMzlkNTQ4MDlkNTQ0NDVhY2IxNjhhYzcmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.AaGGYrkQIZ-geBfWttsyBB2P5isqNTCXO21h25h1Q2k)

<br>

### 5.번개 게시글


![번개 내부](https://private-user-images.githubusercontent.com/50188319/281705178-73e86dc0-4fc3-4bf9-a81b-560de97206a5.PNG?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjI4MTYsIm5iZiI6MTcwNzAyMjUxNiwicGF0aCI6Ii81MDE4ODMxOS8yODE3MDUxNzgtNzNlODZkYzAtNGZjMy00YmY5LWE4MWItNTYwZGU5NzIwNmE1LlBORz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NTUxNlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWNmZTU5MzYwYTBiYjk2YjVmYzgyODViMDM3ZjFmNTI4Y2RjMjY1Y2UyZjU4NzAyMzM4MDBjMTc2ZTJlMTAxZDgmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.UDEVOivKuPtPeqNg4Nd8xpCa5nu-vpePAW57PEeAuTM)

<br>

### 6.번개 채팅방


![채팅방](https://private-user-images.githubusercontent.com/50188319/281705752-d7c5b3d5-d8db-4e9b-963f-bed488a86d0b.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjI4MzEsIm5iZiI6MTcwNzAyMjUzMSwicGF0aCI6Ii81MDE4ODMxOS8yODE3MDU3NTItZDdjNWIzZDUtZDhkYi00ZTliLTk2M2YtYmVkNDg4YTg2ZDBiLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NTUzMVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTJjODA0OTIzMTFlODhlZTMxYzBiZGU5NWMzYzMxZDZhMDUyMDA3ZmQyOThkNDJhOTg0MzMxMzJiMmQyZTQxZTgmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.6SR9LqmqZ39TFgnWYcxVTiakFqUExomNYYTrPCSO_Cc)

<br>

### 7.피드백


 ![피드백](https://private-user-images.githubusercontent.com/50188319/281710993-b891ab67-b4fd-40c0-8c35-322ade5ccd1b.PNG?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjI4NDQsIm5iZiI6MTcwNzAyMjU0NCwicGF0aCI6Ii81MDE4ODMxOS8yODE3MTA5OTMtYjg5MWFiNjctYjRmZC00MGMwLThjMzUtMzIyYWRlNWNjZDFiLlBORz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NTU0NFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTBiOWVjMWMxMjI0MDU4ZjUzNTliOTljZmE0N2MyOTg5ZGUxNDFhMjg1MDY3MmNhOGFhZjE0ZjMyYTVkOTdhZTEmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.2AH3rJM3pLnTX7E5-mqyyubEojUzT9u35C7RrDsVGso)

<br>

### 8.동호회 게시판


![동호회 외부](https://private-user-images.githubusercontent.com/50188319/281714187-1dd73cc9-b534-4389-9087-270f04c35397.PNG?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjI4NTcsIm5iZiI6MTcwNzAyMjU1NywicGF0aCI6Ii81MDE4ODMxOS8yODE3MTQxODctMWRkNzNjYzktYjUzNC00Mzg5LTkwODctMjcwZjA0YzM1Mzk3LlBORz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NTU1N1omWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWUwZmY3MmRlNzBkMTMxMGMxZTBlZmQ2OWNiMmY3OTVmMWYyYzgxZmFjMmUxNzcyNzcxNjBiNjRjNTEyYWFjNTUmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.DZKphxiaJ4HSsnEb4TWOgcaF2YqoJhKpEMhyxEJ2tq8)

<br>

### 9.동호회 게시글


![동호회 내부](https://private-user-images.githubusercontent.com/50188319/281714406-2bcccee1-ebbc-4c66-ab0e-7d2c216eaa44.PNG?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjI4NzAsIm5iZiI6MTcwNzAyMjU3MCwicGF0aCI6Ii81MDE4ODMxOS8yODE3MTQ0MDYtMmJjY2NlZTEtZWJiYy00YzY2LWFiMGUtN2QyYzIxNmVhYTQ0LlBORz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NTYxMFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTg2NTAxYTgyZDFmOTY5MzE1YTZjZGQ1NDE4YmUxNGM2MmQyNmE5ODViZDNhZjc0YTY4ODM2NTlhNzY1ZWE5MjkmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.UaHVr6_OtmGmVegmeJ6s9zItbPbfnCdnPUyK345OiAE)

<br>

### 10.동호회 가입신청 페이지


![가입 신청](https://private-user-images.githubusercontent.com/50188319/281714504-cb63c9fe-311d-4757-90a5-5d8db0969dcf.PNG?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjI4ODUsIm5iZiI6MTcwNzAyMjU4NSwicGF0aCI6Ii81MDE4ODMxOS8yODE3MTQ1MDQtY2I2M2M5ZmUtMzExZC00NzU3LTkwYTUtNWQ4ZGIwOTY5ZGNmLlBORz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NTYyNVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTY1NTllZjk3YWZkOGIwOTg4MDU5YjVhMzFjNDRiODAxYzNhODk4MWE5OWQyYTAwMjIyODBkMTk0NjZmYWFlZjAmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.r1fYYw7LZgOoG-F7Hgk6TWCAK9w_G7VUokf0LhjiI_g)

<br>

### **11. 동호회 공지사항 페이지** 


![공지사항](https://private-user-images.githubusercontent.com/50188319/281714828-755e65e9-cb34-4091-b8ce-23bdd417b03d.PNG?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjI5MDksIm5iZiI6MTcwNzAyMjYwOSwicGF0aCI6Ii81MDE4ODMxOS8yODE3MTQ4MjgtNzU1ZTY1ZTktY2IzNC00MDkxLWI4Y2UtMjNiZGQ0MTdiMDNkLlBORz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NTY0OVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTY0Y2NkMWE0NDc1NGUxM2ZkOWZkODdlMTcyMmZhYmY0NjFlYzg3MWNkZWUzMjc2NDk3YWVhYTlmMTQxMjAyMjEmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.yWeDTgKB35QvuUh7kUMtFEDWrfLcu3TlmhasG5dClLs)

<br>

### 12. 동호회 채팅방


![동호회 채팅](https://private-user-images.githubusercontent.com/50188319/281719664-2e970005-c7d8-4eb7-bdcd-3175cd8bc408.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjI5MzAsIm5iZiI6MTcwNzAyMjYzMCwicGF0aCI6Ii81MDE4ODMxOS8yODE3MTk2NjQtMmU5NzAwMDUtYzdkOC00ZWI3LWJkY2QtMzE3NWNkOGJjNDA4LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NTcxMFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTI0Nzk2NzI1YmQ2MmVmYzIxYjg5NDdjYWEzMmE5ZmY4YTg4NDU3NDdkNzc4NzMwZTQwNDIzYTQ3NWQ3OTJhODkmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.A_ZHNfP6OrYkY_diXUX3ker9BnkTqVFE-12fWOl9sGQ)

<br>

### 13. 동호회 앨범 페이지


![앨범](https://private-user-images.githubusercontent.com/50188319/281724094-398bb700-d67a-4786-8f27-4c18a8b2cb94.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjI5NDcsIm5iZiI6MTcwNzAyMjY0NywicGF0aCI6Ii81MDE4ODMxOS8yODE3MjQwOTQtMzk4YmI3MDAtZDY3YS00Nzg2LThmMjctNGMxOGE4YjJjYjk0LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NTcyN1omWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWRlMTI4MDYwZmNhNWU4NTRhOWFhMTRmZjQwMzFjM2E4Njk3ZmUzZmM0ZGRkZjk3YTFiMTVjNTFjNzRjOTFmNjUmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.fESjZ7AiWRqu5_toqqv9IwScAZVmYzpi5_VdRheRqw0)

<br>
   
### 14. 반응형 모바일 웹



<div align="center">

![모바일](https://private-user-images.githubusercontent.com/50188319/282275905-c240b61b-9af4-4231-a909-2d0f48c89698.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjI5OTIsIm5iZiI6MTcwNzAyMjY5MiwicGF0aCI6Ii81MDE4ODMxOS8yODIyNzU5MDUtYzI0MGI2MWItOWFmNC00MjMxLWE5MDktMmQwZjQ4Yzg5Njk4LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NTgxMlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWMyZTA4MGM2NTE3ZGU0OWIwZjE3MzcxZThkNmQyYmRjODJhNjE5ZWYwZjIzOTcyMWIwNTVlNDVhOWQwMTJmNjMmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.BsMEqK769TJjrZSxSnqHdC4rpsKRmfI4_TrOYkeFx3w)
![모동](https://private-user-images.githubusercontent.com/50188319/282275912-9194f6ef-8235-4a26-9d4e-048fe6f3b217.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjMwMDgsIm5iZiI6MTcwNzAyMjcwOCwicGF0aCI6Ii81MDE4ODMxOS8yODIyNzU5MTItOTE5NGY2ZWYtODIzNS00YTI2LTlkNGUtMDQ4ZmU2ZjNiMjE3LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NTgyOFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTE0MWMzNGJhN2U3MWZmYjgwMDViYTA0ZDQ4MDlhMDQ5NzQ1Mjg4YWRiNzM5MjViMmYzNzQ0NzM2ZDIzZjc2YWMmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.LI9jpqgg8cc7XINd6pPiHVQZ6uhLDj70BYYS40I8TDk)
![모번](https://private-user-images.githubusercontent.com/50188319/282275926-e6db50fe-be54-48a9-88bc-f051ffbe510f.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDcwMjMwMjQsIm5iZiI6MTcwNzAyMjcyNCwicGF0aCI6Ii81MDE4ODMxOS8yODIyNzU5MjYtZTZkYjUwZmUtYmU1NC00OGE5LTg4YmMtZjA1MWZmYmU1MTBmLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDQlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjA0VDA0NTg0NFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTg2OTJmNzk0MDRmN2RjZDI5ZThhMjEyMTI2ODhmZGNiNzlmZTZmNDQ4N2Y3YWE5OTkxNTVhZDJkNTc1YTM0NTImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.nK-S6rFDuSEr65msY7jDN1aMap3Kc-oS4chIntWIm9M)

</div>

---

<br>


# 팀 구성


>## Backend 및 Database : 고경민
       
>## Frontend : 이지호
       
>## Mobile Frontend : 박영민



