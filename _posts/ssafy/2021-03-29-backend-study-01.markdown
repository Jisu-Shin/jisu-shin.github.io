---
layout: post
title: backend-study-01 | Servlet
image: cs7.jpg
date: 2021-03-29
tags: [ssafy]
categories: ssafy
---





# Servlet

- 웹에서 돌아가는 JAVA이다
- 자바를 사용하여 웹페이지를 **동적**으로 생성하는 서버측 프로그램이다
- HTML in Java ( 확장자가 **java**  ) 
- 한 줄 씩 out.println(''\<html>') 하기 귀찮음 



### Web Architecture

1.  Client가 Web Browser 에게 **Data발생한다** // 넘어가는 Data가 Parameter이다
2.  Client가 Server한테 **요청(Request)**한다  
3. **Web server( =http서버) : Client 접속처리** // html,css,js만 처리 가능 
4. <u>DB Server와 Web Serer를 **연결**하기 위해</u> 중간에 **Application Server가 필요**
   - Application Server => `web에서 사용할 수 있는` java사용 => Server Side program (web이 들어가서 // `web+java`)
     - Presentation (화면에다 보이는 역할) -> 5번 동작
     - Business Logic (DB logic)
     - Persistence Logic (DB logic)
   - 톰캣 = Web Server + <u>Application Server</u> (`톰캣을 설치한 이유`)
   - Application Server ----(jdbc프로토콜)---- RDBMS
5.  Server가 Client로 응답(Response)한다



- web.xml : `배치설명서`
  - 서버한테 내가 만든 프로젝트는 ~~한 서블릿이 있어, 서블릿의 이름은 ~~ 라고 설정
  - 많은 Servlet (주가 되는건지, 부가적인건지) 을 구분할 수 있는 설명 파일이다



### web page 이동

1. url 직접입력

2. link ( ex:기사제목누르기... )

3. form

   - GET방식 : 여기 위까지는 다 get방식

   ---

   

   - POST방식 (=> 직접 명시할 때만 )



- Servlet은 서버에서 돌아간다 서버에서 html에서 만든걸 client에 넘겨줘야한다 => IO (이클립스 콘솔처럼)
- 톰캣은 한글 전용이 아니다 / html 로 한글을 넣으면 ? 가 나온다
- 전세계에 제공할 서비스므로 charset=utf-8



### Servlet 역할

1. data get - 데이터를 얻어오기
2. Logic - 데이터를 가지고 일처리 하기 (알맞는 로직에 따라)
3. response page - 결과로 응답 페이지 만들기 (html로 만들기)



- 생성자, init() , destroy() 는 최초 한번만 실행
- doGet(), doPost() 클라이언트가 호출할 때마다 실행
- Servlet객체 한명에 Client 여러명 
- Thread는 WAS가 알아서 처리해줘서 여러 Client가 요청해도 크게 신경쓸 필요 없다
- 네이버는 .nhn  // .do 는 만드는 사람 마음



---
