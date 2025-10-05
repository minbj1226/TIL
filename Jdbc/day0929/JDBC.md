# JDBC (Java DataBase Connectivity)
- Java에서 DBMS와 연동하기 위한 저수준 API(개발자가 원하는 시점에 DB 작업을 할 수 있다.)
- Java.sql 패키지에서 관련 인터페이스와 클래스, 예외를 제공한다.
- Driver loading방식(Driver만 제공되면 모든 DBMS와 연동할 수 있다.)
					 ↑
			DB Vendor사에서 제공하는 bytecode
			배포는 .jar로 배포된다.
			DB Server에 접속하기 위한 DB Client를 bytecode로 제작한 것
			java에서는 windows OS용 JDBC-ODBC Bridge Driver만 제공
			Driver 종류에는 4가지 Type 있다.
			
*Driver type
- type 1: JDNC-ODBC Bridge Driver
	- windows에서만 사용할 수 있는 Driver, DBMS와 연동은 OS에서 설정하고 Java에서 연결하는 방식, 속도가 느리다.
	
- type 2: native driver
	- Driver를 제작한 언어가 Java와는 다른 언어로된 Driver
	- Driver를 사용하기 위해서 별도의 프로그램을 설치해야 한다.
	- Middleware에서 주로 사용
	
- type 3: network protocol driver
	- applet에서 DBMS와 연동하기위한 Driver

- type 4: native protocol driver
	- JDBC에서 가장 많이 사용하는 Driver(빠른 성능과 안정성을 제공)
	- Driver를 제작한 언어가 java언어이므로, Driver를 사용하는 자바프로그램에서는 데이터를 주고 받을 때 문제가 거의 발생하지 않는다. 

-------------------------------------------------------------------   
## JDBC 개발에 사용되는 객체들
- java.lang.Class: DB Vender사에서 제작하여 배포하는 Driver 내 특정 클래스를 객체화하여 JVM에 instance로 올리는 일(Class.forName("oracle.jdbc.OracleDriver"))
- java.sql.DriverManger: JVM에서 로딩된 드라이버를 사용하여 DBMS와 연결을 얻는 일,
getConnection(String URL, String id, String pass)
- java.sql.Connection: DBMS 연결을 유지, Transaction 처리, 쿼리문 생성객체를 얻는 일
- java.sql.Statement: 쿼리문을 실행마다 생성하여 처리하는 객체 
- java.sql.PreparedStatement: 쿼리문을 미리 생성하고, 값을 나중에 넣어서 실행하는 객체
- java.sql.CallableStatement: Procedure를 호출할 때 사용하는 객체(PL/SQL)
- java.sql.ResultSet: 조회결과를 사용하기 위한 객체 (데이터 형을 변환하는 일)
- java.sql.ResultSetMetaData: DD가 없어도 테이블의 MetaData(컬럼명, 데이터형, 크기, null 허용여부) 정보를 얻을 때 사용하는 객체
- java.sql.Types: Procedure에서 처리한 결과를 out parameter에 저장하고 저장된 값을 임시로 저장하기 위해 사용하는 데이터 형을 가진 객체
				  -바인드 변수선언
				  var 변수명 데이터형(크기)		| 	Java에서는 Oracle에 bind 변수를 선언할 수 없기 
				  -프로시저 실행				|	때문에 그 일을 대신 해주는 Types 클래스를 제공
				  exec 프로시저명(값, :변수명

- java.sql.Clob: 자바에서 Clob 데이터 형을 처리하기 위한 객체

--------------------------------------------------------------------
## JDBC 코딩 순서
1. 드라이버로딩(Class)

2. 커넥션 얻기(DriverManager, Connection)

3. 쿼리문 생성 객체 얻기(Statement, PreparedStatement, CallableStatement)

4. 쿼리문 수행후 결과 얻기

5. 연결 끊기 

-----------------------------------------------------------------------
## DBMS와 JVM 연동

1. 드라이버로딩(java언어로된 DBClient) 
``Class.forName("oracle.jdbc.OracleDriver");`` 

2. 로딩된 드라이버를 사용하여 커넥션 얻기
``String url="jdbc:oracle:thin@디비서버위치:포트:SID";``
디비서버위치: localhost, 127.0.0.1, 설정하게 되면 외부에서도 접속이 가능해진
포트: 1521
SID: orcl			

``String id="아이디;"``
``String pass="비번;"``
			
Connection con=DriverManager.getConnection(url, id, pass)
      
---------------------------------------------------------                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    
## SQL문 생성 객체
- Statement, PreparedStatement 인터페이스를 제공

*Statement
- Connection 객체 createStatement()를 호출하여 객체를 얻는다.

``Statement stmt=con.createStatement();``
- 반환된 객체인 Statement는 SQL문을 알지 못한다.
- 쿼리문실행: stmt.executeXxx(String sql)
	- 쿼리문은 실행될 때 마다 계속 생성된다.
	- 동일 쿼리문이 반복 실행될 때 마다 쿼리문이 생성되므로 효율이 좋지 않다.
	- SQLInjection 공격에 취약하다.
	
*PreparedStatement
- Connection 객체 prepareStatement(String sql)를 호출하여 객체를 얻을 수 있다.
``PreparedStatement pstmt=con.prepareStatement(String sql);``
- 반환된 객체인 PreparedStatement는 SQL문을 안다.
- 쿼리문실행: stmt.executeXxx(String sql)
	- 쿼리문은 실행될 때 마다 계속 생성되지 않는다.
	- 쿼리문에 값이 들어가는 위치를 설정하는 bind변수를 사용한다.
	
*CallableStatement
- Connection 객체의 prepareCall("{ call 프로시저명(값,,,) }");
- 프로시저를 호출하기 위한 객체
- bind변수를 사용할 수 있다.(PreparedStatement의 하위 인터페이스)
- SQL문은 Procedure 내 정의되고, 자바에서 프로시저를 호출하여 업무처리한 결과를 얻는다.<br>
=> 자바 코드와 쿼리문이 분리될 수 있다.
