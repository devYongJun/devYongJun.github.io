---
title: HTTP 완벽가이드를 읽고
author: Yongjun
date: 2021-06-15 00:00:00 +0800
categories: [book, http]
tags: [http]
---
![book](../../assets/img/book/httpguide.jpg)

백엔드 개발자로 전직을 위해서 웹의 배경지식을 익히려고 읽은 책이다(꽤 두껍다).

게임개발에서 바이블이라고 불리는 용책이 있듯이 웹개발의 바이블은 이 다람쥐책이 아닐까.. 🐿️

재밌게 술술 읽히는 내용도 있었고, 여러번 다시 봐도 도저히 무슨말인지 이해할수 없는 내용도 있었지만 결과적으로 얻은게 굉장히 많은 책이었다.

나중에 백엔드 경험이 쌓이고 다시 이 책을 읽게 된다면 그때는 지금 얻지 못한 다른 깨달음을 얻을 수 있을 것 같다 .

---

### HTTP (Hypertext Transfer Porotocol)
웹에서 클라이언트와 서버가 데이터를 주고받는 방식으로 현대 인터넷에 공용어라고 말할 수 있다.  
`웹 클라이언트가 웹 서버에서 요청 → 웹 서버가 웹 클라이언트에게 응답`이 하나의 HTTP 트랜잭션이다.

### MIME
웹 클라이언트가 서버에게 요청하는 리소스는 html, txt, jpeg, avi 등 수많은 종류가 있고 이것들을 MIME(Multipurpose Internet Mail Extensions)라는 라벨을 붙여 구분한다.   
MIME 은 `주 타입/부 타입` 으로 구성된 문자열이며 `text/html, image/jpeg, image/gif, video/quicktime` 과 같이 표기한다.

### URI
웹 클라이언트는 웹 서버의 특정 리소스를 식별하는 방식으로 URI(Uniform Resource IDentifier) 를 사용한다.  
URI의 종류로는 URL(Uniform Resource Locator)과 URN(Uniform Resource Name)이 있고 오늘날 대부분의 URI는 URL를 사용하며 `https://dogecoin.com/assets/img/doge.png` 과 같이 표기한다.

### Method
HTTP 요쳥메시지에는 어떤 동작이 수행되어야 하는지 구분하는 메서드 타입이있다.  
주로 쓰이는 메서드 타입으로는 `GET, PUT, DELETE, POST, HEAD` 등이 있다.

### Status Code
모든 웹 서버의 응답에는 상태 코드가 있다.  
이 상태코드로 요청이 성공적으로 처리되었는지, 다른 조치가 필요한지 알수 있고 대표적으로 `200 (성공), 302 (다시 시도), 404 (리소스 찾을수 없음)`등이 있다.  
상태코드에는 텍스트로 이루어진 사유구절도 함께 포함되며 이것은 단지 설명만을 위해서 존재하는것일뿐 실제 응답처리는 숫자로된 코드가 사용된다. 


🚧 틈날때마다 추가 예정