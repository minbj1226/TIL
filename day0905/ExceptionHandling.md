# Exception Handling(예외처리)
-가벼운 에러(프로그램이 동작할 때 문제가 발생하더라도 계속적인 실행이 가능한 에러)
-Exception: 가벼운 문제 상황, 프로그램 동작 중에 exception이 발생하면, exception을 처리한 후 다음 코드로 진행할 수 있다.
-Error: 심각한 문제 상황, 프로그램 동작 중에 error가 발생하면 프로그램이 더 이상 다음 코드로 진행할 수 없다.

## Compile Exception
-bytecode가 제대로 생성되지 못하는 상황에서 발생되는 예외, 소스코드 상에서 에러가 발생하고 IDE가 알려준다.

## Runtime Exception
-bytecode가 생성된 후 실행될 때 발생하는 예외, 메모리에 저장하거나 연산할 때 발생하는 예외 IDE가 알려주지 않는다.

## 예외처리
-try~catch, throws, throw를 사용하여 처리한다.
*try~catch
-throw로 발생된 예외가 throws로 날려지고, try~catch를 사용하여 날려진 예외를 잡아서 처리한다.
-compile exception은 개발자가 반드시 try~catch로 처리해야하고,
runtime exception은 개발자가 반드시 try~catch로 처리하지 않아도 문법 에러가 발생하지 않는다.

문법)
```try{
	예외발생예상코드;
  }catch(예외처리 클래스명 객체명){
  	예외가발생했을 때 사용자에게 제공할 코드들,,,
  }catch(예외처리 클래스명 객체명){
  	예외가 발생했을 때 사용자에게 제공할 코드들,,,
  }finally{
  	사용자에게 반드시 제공되어야할 코드들,,,
  }```
 
*Runtime Exception의 처리(개발자가 try~catch 코드를 누락 가능)
-ArithmeticException: 수에 관련된 예외, 0으로 나눌 때 발생
-ArrayIndexOutOfBoundsException: 배열에 존재하지 않는 인덱스 사용
-IndexOutOfBoundsException: java.util.List에서 존재하지 않는 인덱스 사용할 때
-NumberFormatException: 숫자가 아닌 문자열을 숫자로 변환할 때
-NullPointerException: 객체를 사용하지 않고 사용할 때