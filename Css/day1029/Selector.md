# CSS에서 제공하는 selector들
- embed방식, external file방식에서 사용
- 디자인을 적용받을 태그를 선택하거나, 정의되는 여러 디자인을 하나의 이름으로 묶을때 사용
- selector 종류: id selector, class selector, tag selector, name selector, sub selector, behavior selector, multiple selector 등 제공

형식)
``selector(속성:값; 속성:값; ,,,)``

- 단일 값: 속성:값; display:none;
- 복합 값: 속성:값 값 값; border: 선두께, 선종류 선택

```HTML
<!DOCTYPE html>
<html>
	<head>
	<title></title>
	<style type="text/css">
		<selector{디자인 코드들,,,,}>
	</style>
	</head>
	<body>
	정의된 디자인을 사용하는 tag선언(selector 사용)
	</body>
</html>
```

## ID Selector
- CSS에 정의된 디자인을 HTML `<body>`에서 하나의 태그만 디자인을 사용할 때
- 참조하는 속도가 빠르다.

문법)
1. `<style>` 태그에서<br>
#아이디명{속성:값;,,,}<br>

2. HTML `<body>`의 하위 태그에서<br>
id속성으로 정의된 id의 디자인을 사용<br>

`<태그명 id="아이디명">`

## Class Selector
- CSS에 정의된 디자인을 HTML `<body>`에서 여러 태그가 적용받아 사용할 때 사용
- 참조하는 속도가 빠르다.

문법)
1. `<style>` 태그에서<br>
.클래스명 {속성:값;,,,}<br>

2. HTML `<body>`의 하위 태그에서<br>
class속성으로 정의된 디자인을 여러 번 사용<br>

`<태그명 class="클래스명">`

## Attribute(name) Selector
- CSS에 정의된 디자인을 HTML `<body>`에서 여러 태그가 적용받아 사용할 때
- 태그에 정의되는 모든 속성으로 디자인을 사용할 수 있는 selector

문법)
1. `<style>` 태그에서<br>
[속성명='값'] {속성:값,,,}<br>

2. HTML `<body>`의 하위 태그에서<br>
속성값이 정의된 디자인에서 여러 번 사용<br>

`<태그명 속성명="값">`

## Tag Selector
- CSS에 정의된 디자인을 HTML `<body>`에서 모든 태그가 적용받아 사용할 때
- 태그만 정의되면 디자인을 사용할 수 있는 selector

문법)
1. `<style>` 태그에서<br>
태그명(속성:값;,,,)

2. HTML <body>의 하위 태그에서<br>
정의된 모든 태그에 디자인이 여러번 사용<br>

## Multiple Selector
- 모든 selector에서 적용 가능한 selector
- 하나의 디자인을 다양한 이름의 selector로 사용할 때 사용하는 문법
- selector를 ,로 구분하여 다른 이름의 selector를 사용할 수 있다.
- 디자인 코드의 중복을 최소화하고, 동일 디자인을 다양한 이름으로 사용할 수 있다.
