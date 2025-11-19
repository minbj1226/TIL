# JSP(Java Server Page)
- 동적인 HTML을 생성하기 위해서 
- Servlet 기능 개선
	- 디자이너와 개발자간의 업무 구분이 되지 않는다
	- class 안에서 HTML 코드를 작성하는 방식이므로 복잡도가 향상
	- 서비스를 하려면 DD가 필요
- 확장자가 .jsp인 파일을 생성(java가 아니므로 compile을 하지 않는다)
- WAS에 요청이 발생하면 compile을 수행해준다.
- 웹 디자이너와 개발자간의 업무구분이 어느정도 가능해진다.
- Servlet보다 속도가 느리다.
- DD(web.xml) 설정없이 동작한다.
- Java SE에서 제공하는 모든 기능을 사용할 수 있다.

## CSS(Client Side Script): Front-end에서 실행되는 언어
- JavaScript, ActionScript => HTML 파일에서 작성되고, 클라이언트에서 해석 및 실행되는 언어

## SSS(Server Side Script): Back-end에서 실행되는 언어
- JSP, PHP, ASP => 요청되면 서버에서 해석 및 실행된 후, 동적으로 HTML을 생성하여 응답하는 언어

## JSP 파일 구조

```
<%@ page 속성="값" 속성="값" ,,, %>  선언부 
,							
,
<html>	1. 디자이너(코더)가 HTML 코드 작성
,		2. 개발자 JSP코드 작성(JSP Tags, 내장객체, action tags, EL, JSTL)
,
<html>
```

## JSP Tags
- JSP에서 기능을 정의할때 사용하는 태그들
- 5가지의 태그가 제공
- JSP가 자바로 변경될 때 Servlet으로 생성되고, 사용자에게는 JSP Tag의 내용이 보여지지 않는다.

### JSP TAGS 형식
``<% 코드,, %>``

|태그명|태그|설명|
|------|---|---------|
|지시자 page|<%@ page ,,, %>|JSP페이지에 환경설정용|
|지시자 include|<%@ include ,,, %>|다른 JSP를 끼워넣어 보여줄 때
|선언|<%! %>|JSP에서 method를 정의할 때|
|테스트1|테스트2|테스트3|
