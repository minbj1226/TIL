# Response
- javax.servlet.http.HttpServletResponse가 데이터 형인 객체
- redirect 방식의 페이지 이동, 무조건 다운로드

## Redirect
- response 내장객체에서 제공하는 기능
- sendRedirect()를 사용하여 페이지를 이동
- 정상적인 요청이 있을 때 응답되는 페이지에서, 비정상적인 요청이 발생했을 때 사용하는 페이지 이동 기술

## Redirect 사용법
``response.sendRedirect("이동할 페이지 URL")``

