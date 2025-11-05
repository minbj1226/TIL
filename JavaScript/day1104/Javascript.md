# JavaScript(Front-end 언어: Client Side Script)
- Brenden Eich가 C언어로 개발한 언어
- ECMAScript의 표준 사양을 가장 잘 구현한 언어
- 대부분의 web browser는 ES5를 지원한다.
- 최신버전 ES6이고, transpiler를 사용하여 소스 변환을 하면 web browser에서 실행할 수 있다.
	- transpiler: 특정 언어로 개발된 소스코드를 같은 언어의 다른 버전으로 변환하는 프로그램(ES6 -> ES5 변환: 모든 웹 브라우저에서 실행하기 위해)
	- compiler: 사람의 언어로 작성된 소스코드를 기계어로 변환하는 프로그램(.java -> javac.exe -> .class)
	
## Vanilla JavaScript(Vanilla JS)
- 플러그인이나 외부 library를 사용하지 않는 순수 자바 스크립트(아무것도 설지하지 않아도 동작하는 JS)
- 사용법) inline, embed, external file 방식 3가지 방식으로 사용할 수 있다.

1. inline 방식
- HTML 태그에 직접 정의하는 방식
- 코드의 적용 우선순위가 가장 높다
- 코드의 중복성이 높다
- 복잡한 코드를 작성하기 어렵다
- 구조와 동작이 결합한다

문법)
``<태그명 onXxx="자바스크립트코드">``

2. embed 방식
- HTML에 `<script>` 태그를 작성하고, JS 코드를 정의하는 방식
- 코드의 중복성을 낮출 수 있다.
- HTML 태그와 JS 코드를 분리할 수 있다.

문법)

```JavaScript
<script type="text/javascript">
JS코드
</script>
```

```Java
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
	<title></title>
	<script type="text/javascript">
	JS 코드
	</script>
</head>
<body>

<script type="text/javascript">
JS 코드 
</script>

</body>
</html>
```

3. external file 방식
- 확장자가 .js인 파일을 만들고, 필요한 HTML에서 연결하여 사용하는 방식
- 코드의 중복성이 가장 낮은 방식
- JavaScript Library나 Framework이 개발되고, 배포되는 방식
- .js파일의 파일 인코딩이나 HTML의 `<meta charset="">`과 일치하지 않으면 JS에서 정의한 한글이 깨진다.

사용법)
1. 확장자가 .js인 파일을 생성
2. 필요한 HTML에서 연결하여 사용 
`<script type="text/javascript" src="JS파일 URL">외부 파일과 연결한 <script> 태그에서는 절대로 JS 코드를 사용하지 않는다.</script>`

## 코딩 시 주의사항
- 대소문자를 가린다
- 괄호는 짝으로 정의, (), {}, []
- ;을 생략할 수 있다

## 출력
- alert 출력
	- 경고창으로 출력
	- 코드의 실행을 멈추고 출력(debug용)
	- alert("출력값")
- HTML <body> 출력
	- window.document.write("출력값")
- console 출력
	- 개발자도구 (F12)의 console에 출력 - debug용
	- console.log("출력값")
	
## 주석
- 코드의 실행을 막거나, 코드 부연설명을 기술할 때

## 변수(Variable)
- 프로그램에서 필요한 값을 일시적으로 저장하고 사용하기 위해서
- 가독성 향상
- 변수를 선언할 때 데이터형을 직접 지정할 수 없다(TypeScript은 가능)
- 데이터형은 변수에 값이 할당될 때 동적으로 결정된다(동적 할당)
- hoisting 지원: 아래 라인에서 선언된 변수를 윗 라인에서 사용할 수 있는 것
- 전역변수, 지역변수를 제공
	- 전역변수: JavaScript의 모든 영역에서 사용할 수 있는 변수
	- 지역변수: 함수안에서만 사용할 수 있는 변수
	
### 지역변수
작성법)
1.선언)- 데이터형을 알 수 없다.
`var 변수명;`

2.값 할당)- 데이터형이 결정된다.
`변수명=값;`
숫자: number-11, 문자열: string-'문자열',"문자열" , 불린: boolean-true,false
데이터 형을 확인하는 함수: `typeof(변수명)`

3.값 사용) 
출력, 연산, 재할당<br>
`console.log(변수명)`

### 전역변수
작성법)
1.선언 및 값 할당)- var를 붙이지 않는다.
`변수명=값;`

2.값 사용)
출력, 연산, 재할당<br>
`console.log(변수명)`

## ES6에서 지원하는 변수타입
- 상수: const
사용법)
`const 상수명=값;` -> 값 할당은 선언할 때만 가능

- let
hosting을 막을 때 사용(존재하지 않는 변수를 사용하게 되는 상황을 방지하기 위해서)
같은 이름으로 변수를 중복 선언하지 못하게 막을 때

- var
var는 hosting이 되고, 같은 이름으로 변수 선언을 여러번 할 수 있다.

### 연산자(Operator)
- 연산에 사용되는 예약된 부호들
- 자바와 비슷

1. 단항
`~, !, +, -, ++, --`

2. 산술연산자
`+, -, *, /, %`

3. 쉬프트연산자
`<<, >>, >>>`

4. 관계연산자
`>, <, >=, <=, ==, ===, !=, !===`

5. 논리연산자
- 일반논리: `&&, ||` (여러개의 관계연산자를 묶어서 비교할 때 사용)
- 비트논리: `&, |, ^` (비트를 연산할 때)

6. 삼항(조건)연산자
`?:`

7. 대입연산자
`= , +=, -=, *=, /=, %=, <<=, >>=, >>>=, &=, |=, ^=

## prompt
- web browser에서 제공하는 사용자가 입력 값을 받을 수 있는 객체
- 입력 값은 문자열로 반환한다
- 입력 폼을 만들지 않고, 값을 동적으로 얻을 때 사용

사용법)
`var 변수명=prompt("제공할메시지", "기본값")`

## paresInt
- 정수가 아닌 값(문자열, 실수)을 정수로 변환하는 함수
- NaN: 숫자 아닌 값을 숫자로 변경하거나 연산할 때 발생하는 값

사용법)
`var 변수명=parseInt("값");`

## 제어문
- 프로그램의 순차적인 흐름을 변경하는 문장들

## 조건문
- `if else, switch~case` 모든 데이터 형을 비교할 수 있다.

if) 
- 조건에 맞을 때에만 코드를 실행할 때
```
if(조건식){
	조건에 맞을 때 수행할 문장들,,,;
}
```

if~else) 
- 둘중 하나의 코드를 실행해야 할 때
```
if(조건식){
	조건에 맞을 때 수행할 문장들,,,;
} else if(조건식){

} else{

}
```

switch~case) 
- 일치하는 모든 데이터 형(number, string, boolean, object)를 비교할 때 사용

문법)
```
switch(변수명){
	case 상수: 변수의 값이 상수아 같을 때 수행할 문장들,,,; break;
	case 상수: 변수의 값이 상수아 같을 때 수행할 문장들,,,; break;
	
	default: 비교될 상수가 없을 때 수행할 문장들,,,
}

## 반복문
- 조건에 맞을 때 까지 코드를 반복 실행 해야할 때
`for, while, do~while`

for)
- 시작과 끝을 알 때 사용하는 반복문

문법)
```
for(초기값; 조건식; 증.감소식){

반복 수행할 문장들,,,;

}
```

while)
- 시작과 끝을 모를 때 사용
- 최소 0번 수행 최대 조건까지 수행

문법)
```
초기값;

while(조건식){
	반복수행할 문장들,,,;
	
	증.감소식;
}
```

do~while)
- 시작과 끝을 모를 때 사용
- 최소 1번 수행 최대 조건까지 수행

문법)
```
초기값;

do{
	반복수행할 문장들,,,;
	
	증.감소식;
}while(조건식);
```

## backtick(`)
- JavaScript에서 template literal을 사용할 때 사용하는 특별한 문자
	- template literal: 문자열을 끊지않고 값과 메시지를 혼합하여 사용할 수 있는 문자열
	
- 문자열을 사용하는 모든 곳에서 사용할 수 있다.

사용법)
`문자열 ${변수명} 문자열,,,`
