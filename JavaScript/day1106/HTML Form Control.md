# HTML Form Control의 값 얻기
- 개발자가 필요한 값이 제대로 입력되었는지 판단하기 위해서 => 유효성 검증
- id 속성 사용, name 속성 사용

## id 속성으로 값 얻기
- <태그명 id="아이디">
- HTML Form Control이 `<form>` 태그의 자식태그로 등록되지 않더라도, JS에서 접근하여 값을 얻을 수 있다
- 유일한 id를 사용하기 때문에 checkbox, radio의 확인된 값을 얻기가 불편하다.
- `<form>` 태그는 HTML Form Control들의 입력된 값을 back-end로 전달하기 위해서 사용
- id 속성은 값을 얻는것 보다 디자인을 변경할(DOM) 때 주로 사용
- id 속성만 가진 HTML Form Control은 Back-end로 값이 전송되지 않는다.(name 속성 필요)

사용법)
1. HTML Form Control에 접근(`<form>` 태그가 없어도 접근 가능)
`var node=document.getElementById("아이디");`

2. value 속성으로 값 얻기
`var 변수명=node.value;`

## name 속성으로 값 얻기
- <태그명 name="이름">
- 반드시 `<form>` 태그가 필요
- name 속성을 사용하면 HTML Form Control들은 반드시 `<form>` 태그의 자식 태그로 정의되어야 한다.
- checkbox, radio의 확인된 값을 얻기가 매우 쉽다.
- 중복코드를 줄일 수 있다.

문법)
``(window.document)생략가능, 변수처리.폼이름.control명.value;``

## name 속성의 값이 같은 객체 값 얻기
- checkbox, radio의 값 얻기

문법)
``<input type="checkbox, radio">`` => checked 속성으로 확인된 것의 값을 얻기
``<input type="checkbox" name="hobby" value="a">``보여질 값
``<input type="checkbox" name="hobby" value="b">``보여질 값
``<input type="checkbox" name="hobby" value="c">``보여질 값
``<input type="checkbox" name="hobby" value="d">``보여질 값

1. 객체 얻기(배열)
``var hobbyArr=obj.hobby;``

2. 반복
```
for(Var i=0; i<hobbyArr.length; i++) {
	//확인된 상태를 얻기 .checked
	hobbyArr[i].checked
}
```