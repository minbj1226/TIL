# Media Query
- 반응형, 웹 디자인의 기본이 되는 CSS 속성
- CSS에서 특정스타일을 선택적으로 적용하여 보여줄 때 사용.

문법)
```HTML
@media 미디어타입 and (조건) {

	적용할 CSS 디자인 코드
}
```

- 미디어타입 and
	- 생략가능: screen, print, all
		- screen: 보여지는 화면에 디자인을 작성할 때
		- print: 프린터를사용하여 출력할 디자인을 작성할 때
		- all: 모두 다
	
사용법)
```HTML
@media screen and (조건){

	적용할 CSS 디자인 코드
}
```
- 적용할 CSS 디자인 코드: 보여는 viewport에 넓이를 주로 사용
	- width: 일치하는 넓이였을 때 ( 잘 사용하지 않는다. )
	- max-width: 브라우저의 크기가 설정한 크기보다 작다면 동작
	- min-width: 브라우저의 크기가 설정한 크기보다 크다면 동작

## min-height
- 특정 영역의 데이터가 최소크기를 초과했을 때 자동으로 높이를 변경하여 설정

## z-index
- layer의 순서를 변경할 때 사용
- 대상의 작성 순서대로 1,2,3,,,의 layer 순서를 가진다.

`<div></div>` <- 1<br>
`<div></div>` <- 2<br>
`<div></div>` <- 3<br>

사용법)
`z-index: 숫자`: layer의 순서를 변경할 수 있다.<br>

*방향성
- 디바이스가 가로모드인지 세로모드인지를 검사하여 디자인을 다르게 적용시킬 때 사용
- orientation 속성의 landscape 값을 사용한다.

사용법)
```HTML
@media(orientation: landscape){
	css속성
}
```

## 그림자 설정
- CSS3에서부터 지원되는 속성
- box-shaodw, text-shadow 지원
- 글자에 그림자를 적용

사용법)
`text-shadow: 값 값 값 값;`


- 테두리를 가지는 객체는 그림자 적용할 수 있다.

사용법)
`box-shadow: 값 값 값 값;`

## 둥근 모서리
- border-radius: 속성

사용법)
`border-radius: 값;` (4개의 모서리가 모두 동일하게 호가 만들어진다.)<br>
`border-radius: 값 값 값 값;`