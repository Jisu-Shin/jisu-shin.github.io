---
layout: post
title: backend-study-02 | JSP
image: cs5.jpg
date: 2021-03-30
tags: [ssafy]
categories: ssafy
---




# JSP (Java Server Page)

- Servlet의 단점을 해결하기 위해 사용한다
  - java in HTML
- JSP가 내부적으로 WAS에 의해서 Servlet으로 변환되어서 실행됨
  - 최초 jsp요청시에만 servlet변환 작업이 이뤄진다 // 속도차이는 크게 없다



### JSP 스크립팅 요소 선언

1. 선언 ::  <%! 멤버(전역?)변수와 method 선언  %>
2.  처리문 , 서비스 메소드에 해당하는 영역 , request & response 작업 ::  <% java code %>
3.  출력문 :: <%= 문자열 %> == <% out.println(문자열);  %>
4. 주석 :: <%-- --%>
   - 소스보기 할 때 보이지가 않는다 // html은 주석처리해도 보임
   - 서블릿을 변환될 때 포함을 시키지 말아라



### JSP 지시문

1. Page Directive : 현재 JSP 페이지를 어떻게 처리할지 정보를 제공한다
   - <% @ page atr1="val1"  %>
   - 페이지 맨위에 이클립스가 자동으로 코딩이 되어있다
   - white space 중요, 속성과 속성사이는 띄어쓰기 해줘야한다
   - session의 기본값은 true :: 사용자인증처리, login 
2. include Directive

- 
- session의 기본값은 true
  - 사용자 인증 처리 할 때 사용
- 디버깅이 어렵다는 단점이 있다
- 비즈니스 로직과 프리젠테이션의 분리가 가능하다는 장점이 있다





### JSP 기본객체

**데이터를 담고있는 바구니같은 역할**

--> .setAttribute() , .getAttribute() , .removeAttribute() 공통메소드 

 👇 아래로 내려갈 수록 범위가 점점 커진다

- **pageContext**
  - 현재 page 객체에서만 사용한다
- **request** : 요청은 단 한번만 / 일회성 
  - .setAttribute("o",obj)
  - .getAttribute("o")
- **session**  : 공통적으로 쓸 수 있다 // session = true인 페이지에서만
- application : 모든 프로젝트에서 사용할 수 있다 // 제약사항이 없다 // 프로젝트 바깥으로 나갈 수 없다







서블릿일 경우 httpsession을 만들어야한다

jsp는 미리 만들어 놨다 , 내장 객체









---

