# Web
- WWW(World Wide Web) 또는 W3라고 한다.
- 문자, 이미지, 영상, 소리 등을 포함한 문서(Hyper Text)를 인터넷을 통해 전송하고, 검색할 수 있는 서비스

-internet: Hyper Text를 사용하여 인터넷상의 정보를 검색할 수 있는 프로그램<br>
		   컴퓨터를 프로토콜을 사용하여(TCP/IP) 연결하고, 정보를 주고 받을 수 있는 네트워크(1973년 빈트 서프와 밥 간이 분할되어 있는 네트워크를 하나의 통신망으로 연결하려는 의도를 가지고 명명한 네트워크 
		   
-URL, HTTP, HTML은 영국 Tim berners Lee가 최초 설계.

## Web에서 사용하는 기본 용어
- Hyper Text: 문서 안에서 다른 문서와 연결되는 연결점을 가진 문서
- Hyper Link: 문서간의 이동이나, 하나의 문서 내에서 이동을 하기 위한 링크
- Hyper Media: 영상이나 음성의 미디어를 서로 서로 연결하는 것
- HTML (Hyper Text Makrup Language): Hyper Text를 작성할 수 있는 언어
- HTTP: 웹 서버와 웹 클라이언트간의 통신을 하기위한 통신 규약
- URL: 인터넷에서 존재하는 다양한 자원들을 연결하기 위한 주소 체계<br>
	   프로토콜://호스트명:포트/경로/파일명의 형식으로<br>
	   
## HTML(Hyper Text Markup Language)
- tag언어(<시작태그>내용</끝태그>)
- 언어적인 요소(연산, 제어)가 배제된 그리기(Rendering)하기 위한 언어
- SGML에서 파생된 언어<br>

(images/system_Input.PNG)

*HTML 구조
```hmtl
<!DOCTYPE html>
<html>
	<head>
		<title>타이틀바에 들어갈내용</title>
	</head>
	<body>
		내용
	</body>
</html>
```

*태그
- 줄변경: `<br>, <p>`
- markup: `<big>, <small>, <sup>, <sub>, <u>, <strong>, <b>, <mark>, <strike>`
- 글꼴: `<font>`
- 이미지: `<img>, <map>, <area>`
- 링크: `<a>`
- 목록: `<ul>, <ol>, <li>, <dl>, <dt>, <dd>`
- 글목록: `<h1>~<h6>`
- frame: `<frame>`
- 테이블: `<table>, <thead>, <tbody>, <tfoot>, <tr>, <th>, <td>`
- HTML Form Control: `<form>, <fieldset>, <legend>, <input>, <select>, <option>, <textarea>`
- 특수문자: `&nbsp;, &lt;`

*HTML Service
(images/html.jpg)
web server: HTML을 가지고 있다가, 요청이 발생하면 HTML을 응답해주는 프로그램<br>

web container: Servlet/JSP를 가지고 있다가, 요청이 발생하면 Servlet/JSP를 HTML로 변환하여(동적으로 생성) 응답해주는 프로그램<br> 

WAS(Web Application Service): Java EE의 모든 Spec을 서비스 해줄 수 있는 프로그램<br>