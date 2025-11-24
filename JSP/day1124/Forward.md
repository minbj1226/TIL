# Forward
- 요청 처리 내장 객체(request)를 사용한 페이지 이동
- 웹 브라우저는 페이지의 이동을 모른다.
- 데이터 처리 페이지와 화면 구현 페이지를 분리해서 작성할 때 사용
- RequestDispatcher interface를 사용하여 페이지 이동을 처리

## Forward 사용법
0. 이동할 페이지에서 사용할 값을 설정
``request.setAttribute("이름", Object값);``

1. 이동할 페이지를 설정하여 RequestDispatcher 객체를 얻기
``RequestDispatcher re=request.getRequestDispatcher("이동할 JSP URI");``

2. 이동
``rd.forward(request, response);``

3. 이동한 페이지에서 이전 페이지에 설정된 속성값을 받는다
``클래스명 객체명=request.getAttribute("이름");``

## Forward의 흐름
- 데이터 처리 페이지와 화면 처리 페이지를 분리하기 위해서