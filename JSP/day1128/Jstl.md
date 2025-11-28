# JSTL(JSP Standard Tag Library)
- Java가 아닌 다른 개발사나 단체에서 만들고 배포하는 액션태그
- 표준 액션(액션 태그)에서 지원하지 않는 기능을 제작하여 제공하기 위해서 
- Tag Library 라고 한다.
- 배포가 jar로 되고, Web Application에서 사용할려면 WEB-INF/lib 폴더에 넣으면 된다.

## 사용법
1. 지시자 선언) 외부 tag library와 연결
``<%@ taglib prefix="접두어" uri="Tag Lib를 사용하기 위해서 제공하는 URL"%>``

2. Tag lib에서 제공하는 tag 사용
``<prefix:태그명 속성="값" 속성="값" ,,,>내용</prefix:태그명>``

## core
- 제공하는 기능: 변수선언, 웹 브라우저 출력, 제어문, import, redirect, exception

### 사용법
1. JSTL을 사용하기 위한 지시자 선언
``<%@ taglib prefix="접두어" uri="http://java.sun.com/jsp/jstl/core" %>``
- jsp가 빠진 URL을 사용하면 JSTL에서 EL을 사용할 수 없다.

2. Tag Library에서 제공하는 태그를 사용
``<c:태그명 속성명="값" ,,,/>``

-변수)

선언)
``<c:set var="변수명" value="값"/>``

삭제)
``<c:remove var="변수명"/>``

-웹브라우저로 출력)
``<c:out value="출력할 값" escapeXml="true/false"/>``
- 입력값에 HTML tag가 있다면 tag를 그래도 보여줄 것인지 해석하여 그릴 것인지를 설정하는 속성