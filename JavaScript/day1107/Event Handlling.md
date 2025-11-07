# JavaScript Event Handlling
- Inline 방식: HTML 태그의 onxxx속성으로 이벤트를 발생시키고 처리하는 방식
``<input type="button" onclick="함수명()">`` <- HTML태그와 JS코드가 합쳐진다.

- 이벤트를 등록하여 처리: 익명함수(anonymous function)사용 -> 태그를 찾아서 이벤트 속성에 익명함수를 정의하는 방식

문법)
``document.getElementById("아이디").onxxx=function(){ 이벤트처리코드정의 }``

1. 태그를 찾고 
2. 이벤트 속성에
3. 익명함수로 이벤트가 발생했을 때 사용자에게 제공할 코드를 정의

기명함수(named function)사용 -> 이벤트 리스너에 등록, 태그를 찾아서 이벤트 리스너에 등록

문법)
``document.getElementById("아이디").addEventListener("이벤트의 종류", 함수명 또는 익명함수);``

- 주의: on을 제외한 이벤트명만 사용
	- 클릭이벤트: onclick -> click
	- 체인지이벤트: onchange -> change
- ()를 붙이지 않고 함수명만 할당 -> first class function

## JavaScript 객체
- window: 웹 브라우저의 정보, 하위객체들 접근, 팝업창 띄우기
	- document: HTML 문서에 접근할 수 있는 객체(HTML Form Control 접근해서 조작, DOM)
	- location: 이동할 때 사용
	- history: 웹 브라우저의 방문기록(history)을 사용할 때
	- event: 이벤트의 정보를 얻거나 처리할 때
	- storage: 웹 브라우저에서 값을 저장하고 사용하는 객체
	
* location: 페이지의 이동을 수행하는 객체. (HTML에서는 `<a>, <form>+<input type="submit">`)

사용법)
- href 속성을 사용.(web browser에 history가 남는다.)

``window.location.href="이동할 페이지 url";``



* confirm: 사용자의 의향을 물어본 후 추후 동작을 결정할 때
``var result= confirm("메시지");``

* popup
- 다양한 정보를 전달하기 위해서 만든 창
- 아이디 중복 검사, 우편번호 찾기에 많이 사용

사용법)
1. 창열기
``window.open("팝업창에서 보여질 HTML URL", 창의 아이디, "창의 속성")``
창의 속성: "width=값, height=값, left=값"

2. 자식창에서 부모창으로 값 전달
``opener.window.document.폼이름.control명.value=값``

3. 자식창 닫기
``self.close();``

* 부모창에서 자식창으로 값 전달
- JS에서는 안됨 => Parameter 전송방식을 사용한 JSP에서는 가능

사용법)
1. 부모창에서 자식창으로 전송할 값을 가져와서
``var id=document.frm.control명.value;``

2. QueryString에 붙여서 JSP로 요청
- GET 방식으로 요청할 때 URL 뒤에 ?를 사용하여 붙여서 넘기는 값
- http://localhost/html_prj/day1107/test.jsp: URL
- 이름=값&이름=값&이름=값: QueryString
(http://localhost/html_prj/day1107/test.jsp?이름=값&이름=값&이름=값,,,)

``window.open("test.jsp?id="+id, 창의 아이디, "창속성")``

3. 자식창의 JSP에서 전송되는 QueryString 받기
- scriptlet: <% String id=request.getParameter("id"); %>
- EL: ${param.id}

* history 객체
- web browser에서 이전에 방문한 기록을 사용할 수 있는 객체
- web browser를 닫으면 기존의 방문 기록은 사라진다
- 속도 향상(웹 브라우저는 사용자가 방문한 웹 사이트의 HTML을 저장하고, 뒤로가기나 앞으로 가기를 클릭하면 서버로 요청을 보내지 않고 접속자에 다운로드 되었던 HTML을 보여주게 된다)

