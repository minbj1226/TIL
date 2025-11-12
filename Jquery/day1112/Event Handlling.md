# Event Handlling
- 사용자의 동작이 있을 때, 그 동작에 대한 대비코드를 만들고 실행하는 것

문법)
- on 함수

```
$("selector").on("이벤트종류", 무기명함수(){
	이벤트가 발생했을 때 처리할 코드
});

document.getElementById("아이디").addEventListener("click", First Class Function)
```

- 이벤트 함수

```
$("selector").이벤트함수(무기명함수() {
	이벤트가 발생했을 때 처리할 코드
});
```

## HTML Form Control에 값 얻기
- 이름이 유일한 HTML Form Control
``<input type="text, password,,,">, <select>, <textarea>``

문법)

``var 변수명=$("selector").val();``

- 이름이 중복되는 HTML Form Control
``<input type="radio,checkbox">, <select>``

is()함수를 사용하면 대상에 대한 속성상태를 얻을 수 있다.(true, false)

사용법)
``$("selector").is(":checked"), $("selector").is(":selected")``

*radio,checkbox
- checked 상태일 때만 얻기

``<input type="checkbox" name="chk" class="chk">a``
``<input type="checkbox" name="chk" class="chk">b``
``<input type="checkbox" name="chk" class="chk">c``

1. 대상(checkbox)얻기
``var chkArr=$("[type='checkbox']");````var chkArr=$("[name='chk']")````var chkArr=$(".chk");``

```
for(var i=0; i<chkArr.length; i++) {
	if($(chkArr[i]).is(":checked") { //true나 false인 상태를 얻는다.
		#(chkArr[i]).val() //반복중인 체크박스에 값을 얻는다.
	}
}
```

* each
- 배열과 반복문을 합쳐서 정의할 수 있다.

문법)
- 찾아낸 태그를 바로 반복

```
$("selector").each(function(인덱스를 저장할 변수, 방의값을 저장할 변수) {
	방의값을 저장할 변수
});
```

- 태그를 찾은 후 따로 반복
1. 태그를 찾고

```
var node=${"selector"};``

$.each(배열, function(인덱스, 방의 값을 저장할 변수){

});
```

*select
- selected 상태인 옵션의 값을 얻는다.

``$("selector").val()``

- :eq속성(입력된 인덱스에 해당하는 태그를 찾는속성)
- selector에 eq속성 사용 예)

```
$("selector:eq(인덱스)").함수명();

var sel=$("selector");

for(var i=0; i<sel.length; i++) {
	$("selector:eq("+i+")").is(":selected")
}
```

## HTML Form Control에 값 설정
- 값 설정
``<input type="text, password", <textarea>``

``$("selector").val(값);``

- 상태를 변환(속성 변환)
	- attr 함수(소스코드에 동적으로 속성이 생성), prop 함수(메모리에 동적으로 속성이 생성)를 사용하여 특정태그에 속성을 설정할 수 있다.
	- 하나의 태그에 값을 변경하는 것은 속성값의 변경이 잘 된다.
	- 태그가 다른경우 attr은 속성이 남아 있기때문에 초기화가 안될 수 있다.

- 모든 태그에 속성을 추가하거나, checkbox나 radio의 확인상태를 변경하거나, select의 선택상태를 변경할 때 사용

사용법)
``$("selector").attr("추가할 속성명", 값); //속성을 한번만 설정할 때``
``$("selector").prop("추가할 속성명", 값); //속성을 여러번 설정할 때`` 