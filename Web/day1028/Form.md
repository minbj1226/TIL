# Form
- back-end로 HTML Form Control들의 값을 전송하기 위해서 사용하는 태그
- `<input type="submit">`이 존재하고, 클릭되어야 back-end로 값이 전송된다.
![백엔드-프론트엔드연결](images/backend-frontend.jpg)


사용법)
```HTML
<form action="값을 받을 back-end 페이지 URL" name="이름" id="아이디" method="값을 전송하기위한 방식` enctype="페이지 전송방식">
```

- method: web parameter를 back-end로 어떻게 전송할 것인지를 설정 
	- get방식
	- post방식
	
- enctype
	- Parameter 전송방식(기본 - file이 전송되지 않는다) 
		- application/x-www-form-urlencoded
	- File 전송방식(parameter가 전송되지 않는다)
		- mulitipart/form-data
	
css로 숨김처리를 해서 제공하고, 소스 상에서 영역을 구분하는 용도로 사용	

- `<fieldset>`
	- `<form>` 태그가 가진 HTML Form Control들의 영역을 보여주기 위한 테두리 선

- `<legend>`
	- title border
	
- `<labelfor="커서를 보낼 id명">`
	- 라벨을 설정하는 태그
	
사용법)
```HTML
<label for="name">글자</label><input type="text" id="name">
```