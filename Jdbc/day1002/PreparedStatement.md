# PreparedStatement
- 쿼리문을 미리 만들어두고, bind 변수를 사용하여 값만 쿼리문이 실행되기 전에 넣어서 쿼리문을 DBMS로 전달하는 객체.
- 쿼리문과 값이 분리되어 작성(쿼리문을 작성하는 것이 Statement 보다 용이)
- 쿼리문이 반복적으로 실행되어야 할 때 효율이 좋다.
- SQLInjection이 발생하지 않는다.
- LOB(Large Object)데이터를 처리할 수 있다.

작업순서)
1. 드라이버 로딩
2. 커넥션 얻기
3. 쿼리문을 넣어 쿼리문 생성 객체 얻기
4. 바인드 변수 값 설정
5. 쿼리문 수행 후 결과 얻기
6. 연결 끊기 

## PreparedStatement 동작
//사진 첨부

1. 드라이버 로딩
2. 커넥션 얻기
3. 쿼리문 생성 객체 얻기
``String insertQuery="insert into dept(deptno,dname,loc) values(?,?,?);``

``PreparedStatement pstmt=con.prepareStatement(sql);``

4. 바인드 변수에 값 할당
정수값: pstmt.setInt(바인드변수인덱스, 값)<br> 
문자열 값: pstmt.setString("인덱스", "값")<br>
실수 값: pstmt.setDouble(인덱스, 실수값);<br>
날짜 값: pstmt.setDate(인덱스, java.sql.Date객체);

5. 쿼리문 수행 후 결과 얻기
``int cnt=pstmt.executeUpdate();`` //insert, update, delete(0행~n행), 예외
``boolean flag=pstmt.execute();`` //create, drop, alter, truncate
``ResultSet rs=pstmt.excuteQuery();`` //select, 예외