# 내장 객체
- jspService method안에 선언되어 있는 객체들
- JSP Tag 중 scriptlet (<% %>)과 expression(<%= %>에서만 사용할 수 있는 객체들

|내장객체명|데이터 형|하는 일|
|------|-----|---------------
|request|HttpServletRequest|접속자의 정보를 얻기<br> 요청 web parameter<br> forward 방식을 사용한 페이지를 이동할 수 있는 객체 얻기
|response|HttpServletResponse|응답방식을 설정<br> redirect를 사용한 페이지 이동<br> download<br> Cookie 심기	
|session|HttpSession|관계유지<br> 접속자 별로 데이터를 저장, 관리
|out|JspWriter|JSP에서 발생한 값을 웹 브라우저로 출력
|application|ServletContext|모든 접속자가 사용하게될 공통 값을 저장, 관리					
|pageContext|PageContext|접속자가 접속한 페이지에서만 사용하게 될 값을 저장, 관리
|exception|Throwable|예외처리시 사용<br> page directive에 isErrorPage="true"일때만 제공되는 객체 

## request 내장 객체
- javax.servlet.http.HttpServletRequest가 데이터 형인 객체
- 접속자의 요청 정보를 받는다

URL: web에 존재하는 자원을 요청하는 방식

### HTML Form Control 값 받기
- HTML에서 사용자가 입력한 값을 받기위한 객체들 (`<input>`, `<textarea>`, `<select>`)
- HTML Form Control에 입력된 값은 web parameter로 전달(parameter 전송방식)
	- <form 태그에 감싸져 있을 때에 값이 전송>
	- <form enctype="application/x-www-form-urlencoded">
	- 값은 전송되지만 파일은 전송되지 않는다
	- 파일을 전송하려면 method="post"로 설정하고 enctype="multipart/form-data"로 설정

- request 내장객체를 사용하여 back-end에서 값을 받는다.
*name 속성에 값이 유일(이름이 유일)
``String 변수명=request.getParameter("이름")``

*name 속성에 값이 중복(이름이 중복=>배열로 처리)
``String[] 변수명=request.getParameterValues("이름")``