# 내장 객체
- jspService method안에 선언되어 있는 객체들
- JSP Tag 중 scriptlet (<% %>)과 expression(<%= %>에서만 사용할 수 있는 객체들

|내장객체명|데이터 형|하는 일|
|------|-----|---------------
|request|HttpServletRequest|접속자의 정보를 얻기<br> 요청 web parameter<br> forward 방식을 사용한 페이지를 이동할 수 있는 객체 얻기
|response|HttpServletResponse|응답방식을 설정<br> redirect를 사용한 페이지 이동<br> download<br> Cook							