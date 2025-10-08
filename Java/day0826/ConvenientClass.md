# 편리한 클래스의 사용
- 문자열 관련: String, StringBuffer, StringBuilder, StringTokenizer
- 수학: Math
- 날짜: Date, Calendar, LocalDate, LocalTime, Period, Duration
- 형식: SimpleDateFormat, DecimalFormat
- 난수: Random
- 지역: Locale

## String 
- 짧은 문자열을 다룰 때 사용하는 클래스(중복 문자열을 저장하지 않는다)

## StringBuffer, StringBuilder
- 긴 문자열을 다룰 때 사용하는 클래스
- 객체가 heap 문자열을 직접 저장한다.(중복 문자열을 저장)
- 속도가 빠르다.

*StringBuffer: JDK 1.0에서부터 제공, 속도 느림<br>
*StringBuilder: JDK 1.5에서부터 제공, 속도가 빠름

1. 객체 생성<br>
``StringBuilder sb=new StringBuilder();``
``StringBuilder sb2=new StringBuilder("hello");``
![StringBuilder](./images/StringBuilder.png)

2. method 호출 클래스가 제공하는 일 사용
- 값 붙이기
```java
int i=26;
sb.append(i);

boolean flag=false;
sb.append(flag);
```

- 특정위치에 값 넣기<br>
``sb.insert(인덱스, 값);``

- 특정위치에 값 삭제<br>
``sb.delete(시작인덱스, 끝인덱스+1);``

- 문자열 뒤집기(문자열의 순서 변경)<br>
``sb.reverse();``

## StringTokenizer
- 문자열을 짧은 한 마디로 구분할 때 사용하는 클래스
- java.util 패키지에서 제공하는 클래스를 제공(java.lang 패키지 이외의 패키지는 import 구문으로 해당 클래스를 참조하여 사용할 수 있도록 해야한다.)
- 문자열을 가지고 있지 않고, 문자열의 제어권만 받아서 문자열을 자르는 일을 수행

사용법)
``String data="자바 오라클 JDBC HTML";``

1.생성)기본 공백으로 문자열을 구분<br>
``StringTokenizer stk=new StringTokenizer(data);``

2.토큰의 개수(토큰을 꺼낼 때 마다 크기가 줄어든다.)<br>
``int cnt=stk.countTokens();``

3.토큰이 존재하는지?<br>
``boolean flag=stk.hasMoreTokens();`` //토큰이 존재하면 true, 그렇지 않으면 false

4.토큰(짧은 문자열)을 얻고 포인터를 다음으로 이동<br>
``String token=stk.nextToken();``