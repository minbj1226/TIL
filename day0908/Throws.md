## throws(예외던지기)
-method 안에서 발생된 예외를 던질 때 사용
-throws로 던져진 예외는 호출하는 곳에서 try~catch로 처리 해야한다.
-예외발생 예상코드와 예외처리코드를 분리할 때 사용.
-throws는 method 뒤에 정의한다.
-throws로 던져진 예외는 method 안에서 try~catch를 할 필요가 없다.

문법)
throws 예외처리클래스들,,,,

접근지정자 반환형 method명(매개변수,,,) throws 예외처리클래스들,,,{
	A코드
	예외발생 예상코드
	B코드	
}

호출)
try{
	객체명.method명(값);
}catch(예외처리클래스명 객체명) {
	예외가 발생했을 처리할 코드
}

## throw(예외 강제 발생)
-특정상황에서 예외를 강제로 발생시켜 업무를 처리해야 할 때
-try~catch, throws와 함께 사용.
-사용자 정의 예외처리 클래스와 주로 함께 사용.

문법)
throw new 예외처리 클래스(); //error가 발생하므로, try~catch로 감싸든지, throws로 날림
``public String walk() throws Exception { ``
Exception과 같이 최상위 예외로 던지면 문제가 발생할 수 있는데 어떤 종류의 문제가 발생했는지를 알 수 없다.
=>업무에 맞게 예외처리 클래스를 생성(사용자 정의 예외처리 클래스)

## 사용자 정의 예외처리 클래스
-개발자가 구현하는 업무에 맞는 이름의 예외처리 클래스를 직접 생성하여 사용하는 것
-상속으로 구현 (is a)
-Exception을 상속받아 Compile Exception, Runtime Exception을 상속받아 Runtime Exception을 만들 수 있다.



