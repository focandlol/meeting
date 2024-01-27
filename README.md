## 프로젝트 개요

최근 코로나19가 종식되고 모임이 활성화됨에 따라 사용자들이 더 쉽게 모임을 생성 및 참여할 수 있게 도와주고자 함. 회원 가입 및 로그인, 프로필, 번개 모임(순간적인 모임) 및 동호회(지속적인 모임) 생성 및 참여, 채팅방, 번개 게시판, 동호회 게시판 등의 기능을 구현하여 사용자들이 효율적으로 모임을 생성 및 운영하고 참여할 수 있는 환경을 제공하는 것을 목표로 함. 또한 매너등급 시스템, 호스트의 초대를 통한 참여 기능과 피드백 기능을 통해 모임이 파투 날 확률을 줄이고 사용자에게 깨끗한 모임 환경을 제공.

## 시스템 설계

### 1.기능 설명
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

### 2.개발 환경, 도구 및 언어
![프로젝트 아키텍처](https://private-user-images.githubusercontent.com/50188319/281726710-7fa31809-ec33-490f-8cc7-2c3a720b929b.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDYzMzk3MTksIm5iZiI6MTcwNjMzOTQxOSwicGF0aCI6Ii81MDE4ODMxOS8yODE3MjY3MTAtN2ZhMzE4MDktZWMzMy00OTBmLThjYzctMmMzYTcyMGI5MjliLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAxMjclMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMTI3VDA3MTAxOVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWE4NDlmYjlmZWY0ZTAyNzE4MjRmYmFiNTg3NTViOGFiYTI0ZTM5Zjk1NzgzMmQ0MjVhMTc0NGJmZGJlNTgyNDImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.6cK1V1Xw5js1fP0dc1QFYaQ4KWgpNpXaNZ-1V-64dDs)


### 3.기능 설계

#### 3-1. 메인 페이지
![메인](https://private-user-images.githubusercontent.com/50188319/281681476-d5e1dfdd-d486-40f2-9d82-1a6ee0553f92.PNG?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDYzMzk4NTcsIm5iZiI6MTcwNjMzOTU1NywicGF0aCI6Ii81MDE4ODMxOS8yODE2ODE0NzYtZDVlMWRmZGQtZDQ4Ni00MGYyLTlkODItMWE2ZWUwNTUzZjkyLlBORz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAxMjclMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMTI3VDA3MTIzN1omWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTk5Njg3ZWNlYzg3MGJlMDgxMDE3MDljODgyMWQ0MWM0ZjBlOWVkNWI2ODQ1ZThjN2M2ZDM5YThjYjNhNzdlMzImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.2zENGFy8ZWtm4v8pnTaLTGQk5b6QQkm_HzU-knXaq1g)

#### 3-2. 번개 게시판
![번개1](https://private-user-images.githubusercontent.com/50188319/281681642-a9eb03cc-4826-49dc-99e5-0c5b02377daa.PNG?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDYzMzk5ODEsIm5iZiI6MTcwNjMzOTY4MSwicGF0aCI6Ii81MDE4ODMxOS8yODE2ODE2NDItYTllYjAzY2MtNDgyNi00OWRjLTk5ZTUtMGM1YjAyMzc3ZGFhLlBORz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAxMjclMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMTI3VDA3MTQ0MVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTU3MTM1NGI5NDhkYTA4ODAzOWJlM2M5MTJhODRlYTU0ZjAyNWVkODg4MDI1ZjVmYjBkOWQ4ZjY3OGFmYzAwYzQmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.qsx0R3Rs_yC9MIoEWndITZTsNHKPiw2fTTB83Kow3Nc)
![번개](https://private-user-images.githubusercontent.com/50188319/281680309-9606e337-7117-421a-86b4-4a858731b905.PNG?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDYzNDAwMDMsIm5iZiI6MTcwNjMzOTcwMywicGF0aCI6Ii81MDE4ODMxOS8yODE2ODAzMDktOTYwNmUzMzctNzExNy00MjFhLTg2YjQtNGE4NTg3MzFiOTA1LlBORz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAxMjclMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMTI3VDA3MTUwM1omWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTU4Mjg1OTI3OThmNGI3MjY2ZjA5NzBjZDQ3ZjA4Y2ZiODFlNjIyOWE0MDYzMWEyMzA1YjBiMmU0MjcwZWNmMzEmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.zIwxy2lfiEOdAE5y6sueuIxVndgVHowAQT52l2QtrxQ)

#### 3-3. 동호회 게시판
 ![동호회](https://private-user-images.githubusercontent.com/50188319/281680516-506be925-a811-43bb-99b5-600887d6d8cf.PNG?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDYzNDAwMzQsIm5iZiI6MTcwNjMzOTczNCwicGF0aCI6Ii81MDE4ODMxOS8yODE2ODA1MTYtNTA2YmU5MjUtYTgxMS00M2JiLTk5YjUtNjAwODg3ZDZkOGNmLlBORz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAxMjclMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMTI3VDA3MTUzNFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTA4Yjc1YjBlMjY0NzUzNzVkYmU3ZTIzNDdkNmFjOWExMzMwZGQzM2UwOGE0NjYxYjcwMGUwYjg2MDNmZWQ1MTUmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.mAJOlRnFX0ZqnO4e2LBQphAxzaG3g03k2Kn9jhM_Q9g)

 #### 3-4. 관리자 페이지
 ![구성3](https://private-user-images.githubusercontent.com/50188319/281679503-764dc9a4-fbb3-4b7f-a3c7-790b6d0c372f.PNG?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDYzNDAwOTQsIm5iZiI6MTcwNjMzOTc5NCwicGF0aCI6Ii81MDE4ODMxOS8yODE2Nzk1MDMtNzY0ZGM5YTQtZmJiMy00YjdmLWEzYzctNzkwYjZkMGMzNzJmLlBORz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAxMjclMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMTI3VDA3MTYzNFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWRkZDVhMDk0OWJlZjYxNWVmZjYwYmFkNGJlMzIwMWNjYTg5MjM4M2ZmMGNiMWM5MWI5ZjQ0YzU0OTZkZjVmMmYmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.gmN2zQw4zL_WRaKscFgI8gNPKu37sZFxEkjybh1UFkc)
