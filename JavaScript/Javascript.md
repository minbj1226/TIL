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