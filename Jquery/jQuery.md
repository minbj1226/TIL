# jQuery
- 2006년에 John Resig제작하여 발표한 JavaScript Library
- jquery.com에서 무료로 배포
- write less, do more - 적게 쓰고 더 많은 일을 할 수 있도록 개발된 JavaScript Library
- 단순화한 형태로 가독성이 향상되고, 개발의 효율성이 향상된다.
- 웹 표준을 기반으로 개발(모든 웹 브라우저에서 동작 - cross browsing)
- CSS의 selector를 그대로 사용할 수 있다.
- AJAX(Asynchronous JavaScript & XML)의 단순화
- 배포판은 압축버전과 비압축버전 두 가지를 제공(직접 다운로드하여 사용)
	- 압축버전: compressed version-기계 중심
	- 프로그램 실행에 반드시 필요한 공백 이외에 줄 변경, tab, 주석 등의 기호를 삭제한 파일 => 파일 크기가 줄어든다(속도에 유리)
	- 단: 코드가 읽기 어려움
	- 장: 파일이 가볍다.(다운로드가 빠르게 수행)
	- 파일명에 .min이 들어간다.
	- 비압축버전: uncompressed version-사람 중심
	- 프로그램 실행에 필요없는 줄 변경, tab, 주석 등을 가지고 있는 파일 => 파일의 크가 늘어난다.(속도 불리)
	- 단: 파일이 무겁다.(다운로드가 느리게 수행)
	- 장: 사람이 코드 읽기가 편리
	- 파일명에 .min이 포함되지 않는다.
- CDN(Content Delivery Network)을 통해서 배포	

## jQuery 사용법
1. CDN이나 다운로드 받을 파일을 외부파일방식으로 연결
``<script src="js의 URL"></script>``

2. `<script>`을 새로 열어서 코드 작성
```
<script type="text/javascript">
	순수 JS와 외부 파일방식으로 연결된 .js에서 제공하는 문법으로 코딩
	$(function() {
		var name="민병조";
		if($("#id").val()==""){
			alert("아아");
		}
	});
</script>
```

## jQuery 문법
$ - jQueryObject: jQuery의 기능을 제공하는 객체

```
$("selector").jquery함수(function(){
	코드 정의
});
```

읽기 순서)


## jQuery 로딩
- document 로딩: HTML 문서에 <body> 태그의 태그 정보가 로딩되면 jQuery 실행

```
$(document).ready(function() {

});
```

- window 로딩: HTML문서 <body> 태그에서 사용되는 모든 객체가 로딩되면 jQuery가 실행

```
$(window).load(function() {

});
```

## jQuery selector
- CSS의 selector와 같다
- id selector: 특정 태그 하나 찾을 때

```
$("#id명").기능(function() {

});
```

- class selector: class 속성이 사용된 여러 태그를 찾을 때

```
$(".class명").기능(function(){

});
```

- tag selector: <body>에서 정의되는 모든 태그를 찾을 때

```
$(".class명").기능(function(){

});
```

- attribute selector: "속성=값"과 일치하는 모든 태그를 찾을 떼

```
$("[속성명='값']").기능(function() {

});
```

- sub selector: 특정 상속관계의 모든 태그를 찾을 때

```
$("부모태그 > 자식태그").기능(function() {

});
```

- behavior: 지원하지않고 함수로 제공한다.

```
$("부모태그:동작").기능(function() {

});
```