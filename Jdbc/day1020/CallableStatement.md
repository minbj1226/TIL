# CallableStatement
- Procedure를 호출하기 위해 자바에서 제공하는 객체
- PreparedStatement의 자식 인터페이스(bind 변수를 사용)

## 1.Procedure
- PL(Procedure Language)/SQL에서 제공하는 기능 중 하나.
- Procedure에서 제공하는 기능: 기본문법, 연산자, 제어문, cursor, procedure, function, trigger, package
- 화면이 다양하게 제공되어야하는 환경에서 사용.(업무로직을 분리하여 만들 수 있다.)
- 프로그램의 연속성을 가지게 할 수 있다.(프로그램 실행 도중에 다른 결과를 얻을 수 있다.)
- DBMS에서 정보 관리뿐만 아니라, 업무로직까지(연산+제어)를 정의할 수 있다.
- 작성된 Procedure는 user_procedures DD에서 확인 가능
- auto commit이 되지 않고, 개발자가 조건을 설정하여 commit이나 rollback을 수행
- 반환형이 없고, out parameter를 사용하여 필요한 만큼 값을 반환할 수 있다.

순서) 코드작성 -> 컴파일 -> 실행(직접실행)<br>
주의: 문장의 끝에는 ;을 넣는다.

작성법)
```
create or replace procedure 프로시저명(변수명 타입 데이터형, 변수명 타입 데이터형,,,)
is 
	변수선언, cursor 선언(여러행 조회), recode 선언(여러개의 값을 묶어서 사용하기 위해-DTO와 비슷), table 선언(여러 값을 한 번에 모아서 처리하기 위해 사용-배열과 비슷)
begin
	업무로직 작성
exception
	예외처리
	
end;
```

변수명 타입
- in parameter: 생략 가능, 프로시저 외부의 값을 프로시저 내부로 전달할 때 사용.<br>
사용법) 변수명 데이터형, 변수명 in 데이터형

- out parameter: 생략 불가, 프로시저 내부 값을 프로시저 외부로 전달할 때 사용.<br>
사용법) 변수명 out 데이터형

## 2.저장
``프로시저명.sql``

## 3.컴파일
``@경로/파일명.sql``

## 4.에러보기
``show error``

## 5.바인드변수 선언
- 프로시저가 실행한 결과를 저장하기 위해 sqlplus에 선언하는 변수
``var(variable) 변수명 데이터형(크기)``

## 6.실행기를 사용하여 실행(직접 실행)
``exec(execute) 프로시저명 (값,,,:바인드변수명,,)``
- 바인드변수명: out parameter가 내보내는 값을 저장하기 위한 변수

## 7.바인드변수에 저장된 값을 출력
``print 바인드변수명 바인드변수명``

PL/SQL 연산자
- SQL과 동일
- 대입연산자: =