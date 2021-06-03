---
layout: post
title: backend-study-04 | EL
image: cs2.jpg
date: 2021-04-01
tags: [ssafy]
categories: ssafy
---



# EL



- Jsp의 식
  - <%=request.getParameter("num")%>
- Jstl의 식
  - <c:out value = "${param.num}"/>
- EL의 식
  - ${param.num}



Jstl 을 쓰기 위해서 EL사용?



sendRedirect하는 이유

dispatcher.foward 두점의 차이 

=> mvc 구조에서는 1.fc -> 2. controller -> 3. service -> 4 dao ->5.controller, jsp -> 화면이 만들어진다 

=> 화면이 있을 때 바로 실행시키면 안된다 자기가 실행되기전에 db 갔다오는 

=> return 값 :: 모든걸 request에 저장한다 데이터들이 안에 있음 // request.setAttribute

=> jsp는 request는 꺼내서 사용한다

// dispatcher로 할 경우 꺼내서 쓸 데이터가 없다 





executeQuery() executeUpdate() 두가지의 차이 : select의 차이 구분해서 써야 성능이 좋다 

select->  Query

drop,delete,update... 나머지는 -> executeUpdate





db server, client요청이 오면 하는게 아니라 미리 만들었다가 왔다갔다 해줘라

db가 있으면 connection pool을 만든다 거기 안에 연못안에 (`connection`)이 있다

이미 pool이 만들어져있다 db 네트워크 연결을 미리 해놓았다 

client요청을 받고 dao까지 오면 dao가  connection을 <u>빌려오고</u> db작업을 다했으면 <u>반납한다</u>

상용서비스에는 중요,,,,,, 