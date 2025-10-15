# PreparedStatement의 like 사용
- 문자열 중에서 일부분의 데이터만 알고 있을 때, 검색, 변경, 삭제 작업을 해야하는 경우
- PreparedStatement의 bind변수(?)는 like '%' 특수문자와 함께 사용되면 인식이 되지 않는다.

``String sql="select 컬럼명,, from 테이블명 where 컬럼명 like '%?%'";`` <- 입력된 쿼리문에 %문자와 바인드 변수가 함께 사용되면 바인드 변수를 인식하지 못한다.<br>

``PreparedStatement pstmt=con.prepareStatement(sql);``

//바인드 변수 값 설정
pstmt.setString(1, "값");

해결) => %를 일반문자로 인식 시키고('%') 바인드 변수(?)는 문자열 붙임연산자('||')로 처리하면 인식
``String sql="select 컬럼명,, from 테이블명 where 컬럼명 like '%'||?||'%' ";``