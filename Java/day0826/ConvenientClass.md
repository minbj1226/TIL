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

1. 객체 생성
StringBuilder sb=new StringBuilder();
StringBuilder sb2=new StringBuilder("hello");
![StringBuilder](./images/StringBuilder.png)

2. method 호출 클래스가 제공하는 일 사용
- 값 붙이기
```java
int i=26;
sb.append(i);

boolean flag=false;
sb.append(flag);
```

- 특정위치에 값 넣기
``sb.insert(인덱스, 값);``

- 특정위치에 값 삭제
``sb.delete(시작인덱스, 끝인덱스+1);``

- 문자열 뒤집기(문자열의 순서 변경)
``sb.reverse();``
