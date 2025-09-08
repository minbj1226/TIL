##예외메시지 출력
-catch 안에서 예외처리 객체가 제공하는 예외 메시지를 출력할 수 있다.
(개발자가 확인해야하는 메시지와 일반 사용자가 확인해야하는 메시지는 다르다.)

-XxxException 클래스에서는 예외 메시지를 출력할 수 있는 method를 제공한다.

-예외 메시지는 비정상적인 상태의 출력 메시지이므로 표준출력 스트림(System.out)보다는 표준 에러 출력 스트림(system.err)을 사용하는 것을 권장한다.
ex)System.err.println("에러 출력 메시지");

1.간단한 메시지만 출력
String msg=예외처리객체명.getMessage();

2.예외를 처리하는 예외처리 클래스와 간단한 메시지 출력
toString()
System.err.println(예외처리 객체명);

3.자세한 예외 정보 출력
예외처리객체명.printStackTrace();