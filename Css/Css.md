# CSS (Cascading Style Sheet)
- 하콩 비움 리가 1994년 제안한 Style Sheet 언어
- 웹 디자이너가 주로 사용하는 Style Sheet 언어
- 웹 페이지에서 통일성 있는 디자인을 제공할 때
- CSS의 대표 Framework-bootstrap
- 3가지의 방법으로 사용할 수 있다.
	- inline, embed, external file
- CSS는 에러가 발생하지 않는다.

문법)
속성: 값

사용법)
*inline 방식
- HTML tag에 style 속성을 사용하여 직접 정의하는 방식
- selector가 사용되지 않는다(디자인 적용받을 태그에 직접 작성하기 때문에 selector가 필요x)
특징: 디자인 적용 우선 순위가 가장 높다.<br>
단점: 디자인 코드의 중복성이 가장 높다.<br>

문법)
``<태그명 style="속성: 값; 속성: 값; 속성: 값;,,,">``

*embed 방식
- HTML의 <head>태그 사이에 <style>태그를 정의하고, 디자인 코드를 작성하는 방식
- external file 방식보다는 적용 우선순위가 높다
- 디자인 코드의 중복성을 낮출 수 있다.
- selector가 사용된다.

## Web Site
- 대상: 일반사용자
- 별도에 사용자 교육 없이 사용 가능
- 업무 로직이 복잡하지 않다
- web agency에서 주로 개발(PHP,ASP,JSP)

## Web Application
- 대상: 기업에서 일을 하는 사원
- 별도의 사용자 교육이 필요
- 현업의 업무를 알아야 하기 때문에 구현의 난이도가 web site보다 높다.
