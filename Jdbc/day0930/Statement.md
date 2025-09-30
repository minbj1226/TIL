## Statement의 사용
1. 드라이버로딩
2. 커넥션 얻기
3. 쿼리문 생성객체 얻기(Statement)
``Statement stmt=con.createStatement();``
4. 쿼리문 수행 후 결과 얻기
``int deptno=50;``
``String dname="개발부";``
``String loc="서울";``

*출력했을 때 SQL의 쿼리문 형식으로 출력되어야 한다, 쿼리문 끝에 ;을 붙일 수 없다.
``String insertQuery="insert into dept(deptno,dname,loc) values("+deptno+",'"+dname+"','"+loc+"')";``

```java
int rowCnt=stmt.executeUpdate(inserQuery);

if (rowCnt == 1){ 	5.연결 끊기
	추가성공			stmt.close();
}
					con.close();
```

## JDBC SQL 실행 메서드 정리

| SQL 구문 종류             | DBMS 영향 | 대표 예시                           | 사용 메서드             | 반환값/결과           |
|----------------------------|-----------|------------------------------------|-------------------------|-----------------------|
| **데이터 조회**            | X         | `SELECT`                           | `executeQuery()`        | `ResultSet` (행 집합) |
| **데이터 변경**            | O         | `INSERT`, `UPDATE`, `DELETE`       | `executeUpdate()`       | int (영향받은 행 수)  |
| **DDL (스키마 변경)**      | O         | `CREATE`, `DROP`, `ALTER`, `TRUNCATE` | `execute()`            | boolean (성공 여부)   |

## J2EE 패턴
- Enterprise Application에서 사용하는 패턴

### DAO(Data Access Object) Pattern
- 업무로직(BO: Business Logic)과 데이터 베이스 코드(DAO)를 분리한 패턴
:유지보수가 쉬워진다. 
