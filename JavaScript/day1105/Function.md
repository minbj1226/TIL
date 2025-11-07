# Function(함수)
- 자주 사용될 기능을 미리 구현해놓고, 필요한 곳에서 호출하여 사용하기 위해
- 코드의 중복성을 최소화할 수 있다
- 업무를 구분하여 작성할 수 있다
- built-in function(JS 내에서 제공하는 함수), user define function(개발자가 선언하여 사용하는 함수) 두 가지를 지원
- 반환형이 없다(개발자가 데이터 형을 지정할 수 없기 때문에 반환형을 설정할 수 없다.)
- 반환 값이 필요하다면 가장 마지막 줄에 return을 기술하면 된다.
- 익명 함수, 기명 함수 두 가지로 작성할 수 있다.

- 기명 함수: name function
작성법)
```
function 함수명(매개변수,,,){

	return 값;
}
```

호출)
```
함수명(값,,,)
var 변수명=함수명(값,,,);
```

- 무기명 함수: anonymous function
작성법)
```
var 변수명=function(매개변수,,,){
	
	return 값;
}
```

호출)
```
변수명(값,,,)
var 변수명=변수명(값,,,);
```

anonymous function은 이름이 없음 => 호출 불가 => 함수를 변수에 할당하여 사용.
함수가 값으로 취급된다. => first class function

## 사용자의 동작에 따른 함수호출
- HTML 태그에서 onXxx=""속성을 사용하여 사용자의 동작을 감지하고, 자바스크립트 함수를 호출한다.

사용법)
`onXxx="자바스크립트 함수 호출, 한 줄로 작성 가능한 코드 기술"`

## HTML 영역에서 JavaScript영역으로 변경
- HTML 태그에 속성을 정의하는 부분은 HTML 영역이므로 HTML 관련 코드만 정의할 수 있다.

`<태그명 속성="값">`

`<a href="함수()">호출</a>` <- HTML 영역에 "함수()"가 존재하지 않으르모 error가 발생

- 영역 변경
영역: javascript을 붙여주면

## 함수의 매개 변수
- ES6에서는 함수의 매개변수에 초기 값을 설정할 수 있다.
- 함수 호출시 arguments를 입력하지 않으면 설정된 값이 기본적으로 입력된다.

```
function 함수명(매개변수=초기값,,,) {

}
```

## 내장 함수
- 수학 함수
`Math.abs(), Math.round(), Math.floor(), Math.ceil(), Math.random()`

## 문자열 함수
- 문자열의 길이는 length keyword를 사용
`length()` -> 함수로 제공되지 않기 때문에 ()를 붙ㅇ이면 error가 발생
- 문자열 같은지 비교 (==으로만 비교)
`"문자열".equals(비교할 문자열)` -> 사용 불가

## 지정한 시간에 지정한 함수를 호출하는 함수

`setTimeout(호출할 함수명, ms);`

- 주의: 함수명만 입력하여 setTimeout 함수 안에서 입력받은 함수를 호출할 수 있도록 해 주어야 한다.(First Class Function)

```
function test() {
	alert("test function");
}
```

```
function test2(func) {
	func();
}
```

- 호출: `test2(test)`