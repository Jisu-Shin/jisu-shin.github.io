---
layout: post
title: backend-study-03 | MVC
image: cs6.jpg
date: 2021-03-31
tags: [ssafy]
categories: ssafy
---




# MVC Design pattern


- Model : Business Logic / Data  (Java)
- View : GUI / Design / Presentation (JSP)
- Controller : View - Model 사이의 상호동작 관리 (Servlet)



M <- C -> V

1. 컨트롤러가 먼저 요청, 작업을 받는다 (HTTP Request)
2. 컨트롤러가 모델(DB작업..등등등...)을 부른다 
   - 실행할 때 필요한 parameter로 보낸다
3. 모델이 작업한 결과를 컨트롤러가 받는다
4. 컨트롤러가 모델이 작업한 결과를 뷰한테 전달한다
5. 뷰가 화면을 만든걸 (GUI Content) 컨트롤러한테 보내주고
6. 컨트롤러가 브라우저한테 보내준다 (Http Response)



browser = client

---



| Client | Controller                                                   |                                              | ③ Service                                                    | ④ DAO                                                        | DB   |
| ------ | ------------------------------------------------------------ | -------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ---- |
|        | ① Front Controller                                           | ② controller                                 |                                                              |                                                              |      |
|        | 1. client로 부터 들어오는 요청 받기<br>2. 요청구분 -> controller에게 전달 | F.C로 부터 요청을 받아 처리                  | DAO의 여러작업을 묶어서 수행가능 <br>트랜잭션처리 같은거..?<br> 출금+입금+계좌확인 | client 요청에 대한 일제 처리 (DB)<br>DB에 대한 단위 작업만 수행 <br>한 메소드에서 한개만 (출금//입금//계좌확인) |      |
|        |                                                              |                                              | controller로부터 요청 받아서 처리                            | [CRUD] <br> [isert, select, update,delete]                   |      |
|        |                                                              | ⑤ JSP(View)<br>결과를 같이 jsp한테 준다 <br> |                                                              |                                                              |      |

기능별로 나눈거 음식점처럼

가게에서 손님 받는 사람 / 홀에서 받는 사람 / 

FC는 client한테 요청을 계속 받을 수 있다

부담이 덜해진다 , 오버헤드를 낮춘다

C는 전달 받은 것만 처리한다