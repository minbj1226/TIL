# 출력
- html함수, text함수 사용
- 원하는 태그에 내용을 모두 삭제한 후 입력되는 값을 출력한다.

사용법)

``$("selector").html("출력코드");`` <- innerHTML과 같다, 출력 코드에 HTML tag가 있다면 태그를 그려서 보여준다.

``$("selector").text("출력코드");`` <- innerText와 같다, 출력 코드에 HTML tag가 있다면 태그를 그리지않고 그대로 보여준다.

----

# 함수

## CSS 함수
- selector로 선택된 대상에 stylesheet를 설정하거나, 설정된 CSS 속성값을 얻을 때 사용
- tag에 설정된 style값 얻기

``var 변수명=$("selector").css("속성명")``

- tag에 설정된 style값 설정

``var 변수명=$("selector").css("속성명","값")``

- style 태그에 정의한 class 속성 사용

``addClass("클래스명")``
<style>태그 내의 선언된 class 속성을 jQuery에서 설정할 때 사용하는 함수

사용법)

```
<style type="text/css">
.클래스명{디자인코드,,,} //여러 디자인 속성을 하나의 클래스명으로 묶을 수 있다.
</style>

$("selector").addClass("클래스명"); //클래스에 해당하는 여러 디자인을 한번에 설정할 수 있다, 기존의 디자인 속성이 유지된다.
```

- removeClass 사용
selector로 찾아낸 태그에서 해당 클래스 속성을 제거할 때 사용하는 함수

사용법)
``$("selector").removeClass("클래스명")``