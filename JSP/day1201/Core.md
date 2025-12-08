# 제어문
- scriptlet 없이도 JSTL을 사용하면 제어문을 사용할 수 있다.
- 조건문: if, choose(when, otherwise)
- 반복문: forEach, forTokens

## if 문법
- 단일 if만 지원

```
<c:if test="">
	조건에 맞을 때 실행할 문장들
</c:if>
```

## choose 문법
- 여러 조건을 비교할 때(다중 if)

```
<c:choose>
	<c:when test="조건식">
		조건에 맞을 때 수행할 문장들,,,
	</c:when>
	<c:when test="조건식">
		조건에 맞을 때 수행할 문장들,,,
	</c:when>
	
	<c:otherwise>
		모든 조건에 맞지 않을 때 수행할 문장들
	</c:otherwise>
</c:choose>
```

## 반복문
- forEach: 인덱스를 출력하거나, 배열 java.util.Collection을 반복하여 모든 방의 값을 출력할 때 사용

- 인덱스만 출력

문법)

```
	<c:forEach var="변수명" begin="시작값" end="끝값" step="증가값">
		반복수행할 문장들,,,
		EL에서 var의 변수명을 사용하면 begin에서부터 end까지의 값을 출력할 수 있다.
	</c:forEach>
```

## 배열, java.util.Collection 출력
- 주의: 숫자를 출력하는 속성은 사용하지 않는다(begin, end, step)

문법)

```
<c:forEach var="변수명" items="${ 배열명, Collection명 }" varStatus="증가하는 값을 저장할 변수">
	${ 변수명 }
</c:forEach>
```

### 배열, java.util.Collection 사용법

```
<%
//1. 배열, Collection 생성
String[] arr={값,,,};

//2. scope 객체에 저장 => EL에서 직접 사용할 수 없다.
pageContext.setAttribute("이름", arr);
%>

//3. 반복
<c:forEach var="ele" items="${ scope 객체명 }" varStatus="i">

${ i.count } ${ele}
</c:forEach>
```

## fmt
- 날짜, 숫자 형식을 변경하여 출력할 때

## fmt 사용법

1. 지시자 선언)
``<%@ taglib prefix="fmt" uri="http://java.sun.com/jsp/jstl/fmt"/>``

2. 숫자 변환)
``<fmt:formatNumber value="출력할 숫자" pattern="출력형식"/>``
- 출력형식이 0이면 해당자리에 데이터가 없다면 0을 채워서 출력, #이면 데이터가 있는 부분까지만 출력

3. 날짜 변환) 원하는 형식의 날짜로 변환
``<fmt:formatDate value="날짜 객체" pattern="SimpleDateFormat의 날짜패턴"/>``
