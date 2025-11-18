# Servlet Lifecycle
- 일반 클래스는 생성자(1번 호출) > method(여러번 호출) > finalize(객체가 소멸될때 1번 호출) 생명 주기를 가진다.
- 생명주기 method는 GenericServlet에서 제공
`init()`: 최초 접속자에 의해 1번만 호출(생성자의 코드를 정의)
``doGet,doPost,service``: 모든 접속자가 요청했을 때 호출되는 method - 여러번 호출
`destory()`: WAS가 정상종료되어 Servlet 객체가 소멸될 때 1번 호출되는 method

## Servlet 호출
