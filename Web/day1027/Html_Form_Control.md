# HTML Form Control
- 사용자가 입력하는 값을 받기 위해 HTML에서 제공하는 객체들
- ``<input>, <select>, <textarea>`` 3가지 객체가 제공.
- `<form>` 태크의 자식태그로 포함된 HTML Form Control의 입력 값들이 서버(back-end)로 전송될 수 있다.

* `<input>`
- 사용자가 입력하는 값을 받기위해 다양한 객체를 제공
- type 속성에 따라 제공되는 객체가 다르다.
- 공통속성: name="이름" id="아이디" class="클래스명" readonly="readonly" disabled="disabled" value="보여질 글자" type="생성할 객체"
	- 읽기전용: 편집불가, 입력되어진 값이 back-end로 전송된다.
	- 비활성화: 편집불가, 입력되어진 값이 back-end로 전송되지 않는다.
	
1. text
```HTML
<input type="text" name="이름" id="아이디" class="클래스명" size="넓이" maxlength="최대입력글자수" readonly="readonly" disabled="disabled" value="보여질 글자" placeholder="보여질 글자"/>
```

- name: Back-end로 값이 전송되어야할 때 필요한 속성
- id, class: JavaScript이나 CSS HTML Form Control에 접근하기 위한 속성
- value: 값이 입력되더라도 value 값은 유지, back-end로 전송
- placeholder: 값이 입력되면 값이 사라진다, back-end로 값이 전송되지 않는다.

2. password 
```HTML
<input type="password" name="이름" id="아이디" class="클래스명" size="넓이" maxlength="최대입력글자수" readonly="readonly" disabled="disabled" value="보여질 글자" placeholder="보여질 글자"/>
```

3. checkbox
```HTML
<input type="checkbox" name="이름" id="아이디" class="클래스명" readonly="readonly" disabled="disabled" value="back-end로 전송할 값" checked="checked"/>
```
- checked: 체크박스가 확인된 상태로 제공되어야 할 때

4. radio
```HTML
<input type="radio" name="이름" id="아이디" class="클래스명" readonly="readonly" disabled="disabled" value="back-end로 전송할 값" checked="checked"/>
```

- name: name 속성의 값이 같아야 그룹으로 묶여진다.