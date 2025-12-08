# DBCP(DataBase Connection Pool)
- JDBC 방식에서 Connection 관리방법을 개선한 방식
	- JDBC: DB연동이 필요한 작업이 있을 때 마다 Connection을 계속 연결하고, 끊는 방식
	- 장점: 필요한 때 마다 연결을 얻고, 해제하기 때문에 메모리를 절감할 수 있다.
	- 단점: 초기지연시간 발생
- 일정 개수의 커넥션을 미리 연결해두고, 필요한 때 꺼내서 커넥션을 사용하는 방식
	- 장점: 초기 지연 시간이 줄어든다, 커넥션의 재사용성이 향상
	- 단점: 메모리의 낭비
- tomcat은 설정을 통해서 DBCP를 사용할 수 있다.
- tomcat에서 제공하는 DBCP명 project마다 설정하고, 독립적으로 사용한다.

## DBCP 사용법
1. DBMS에서 배포하는 driver(.jar 배포)를 CATALINA_HOME/lib 설치
2. DBCP가 필요한 `<context>`에 DBCP 설정

```
<Context path="/jsp_prj" docBase="/jsp_prj">
<Resource name="jdbc/myoracle" auth="Container"
              type="javax.sql.DataSource" driverClassName="oracle.jdbc.OracleDriver"
              url="jdbc:oracle:thin:@127.0.0.1:1521:mysid"
              username="scott" 
              password="tiger" 
              maxTotal="20" 
              maxIdle="10"
              maxWaitMillis="-1"/>
```