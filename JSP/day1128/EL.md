# EL(Expression Language)
- 표현언어: JSP에서 웹 브라우저 출력을 목적으로 만들어진 언어
- page directive에서 isELIgnored="false"인 설정상태에서 사용할 수 있다.
- 변수 값(직접 출력 불가하고, scope 객체에 할당 후 출력), scope객체의 값, web parameter의 값, 간단한 연산 결과를 web browser로 출력할 수 있다.

## 사용법
`${ 코드 }`

*EL에서 변수 출력
- EL에서는 변수를 직접 출력할 수 없고, scope 객체에 할당해야 출력할 수 있다.

*scope
pageContext, request, session, application
=> 값 설정 .setAttribute("이름", "값")

EL에서 사용할 때는 scope 객체를 지원하는 객체를 제공

*Scope객체 => EL에서 지원하는 scope 객체명
pageContext => pageScope
request => requestScope
session => sessionScope
application => applicationScope

사용법)
1. scope객체에 값 할당

```
<%
pageContext.setAttribute("이름", "값");
%>
```

2. EL에서 scope 객체의 이름으로 변수값 얻

``${ pageScope.이름 }``