# 정렬
- 글자 정렬과 객체 정렬 두 가지를 제공
- 글자 정렬
	- 수평 정렬) text-align: 값;
		- 값: left, center, right
	- 수직 정렬) vertical-align: 값;
		- 값: top, middle, bottom
		
## 객체 정렬
- text-align으로 정렬되지 않는 태그(대상)들을 객체라 한다.
- 수평 정렬만 가능
- `float`: 객체를 왼쪽, 오른쪽으로 정렬할 때 사용하는 속성

사용법)
float: 값;

주의: float 속성을 사용하여 정렬을 수행하면, 하위 객체로 정렬속성이 전파되는 경우가 발생할 수 있다. 이 경우 float속성의 하위 전파를 막으려면 clear:both 속성을 사용한다.

selector{ float:right }
selector{ 정렬속성을 가지지 않는 디자인 코드 }
