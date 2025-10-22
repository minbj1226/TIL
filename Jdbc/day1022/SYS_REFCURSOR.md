# SYS_REFCURSOR
- PL/SQL에서 여러 행을 조회하여 반환하기 위한 cursor.
- out parameter로 SYS_REFCURSOR를 사용하면 조회쿼리는 procedure안에서 수행하고 제어권을 외부로 내보낼 수 있다.
- 프로시저를 호출하는 곳(SQLPlus, Golden, Java)에서는 커서를 받아서 사용.

순서)
1. 프로시저실행 -> 2. REFCURSOR의 제어권을 받고 -> print 커서명(조회 결과가 출력)

사용법)
1. out parameter로 SYS_REFCURSOR 선언
``create or replace procedure 프로시저명(커서명 out SYS_REFCURSOR)``

2. 프로시저 안에서 커서를 선언
``open 커서명 for select 컬럼명``

## SYS_REFCURSOR를 java에서 받기
- Types.REFCURSOR field를 사용하거나 oracle.jdbc.OracleTypes.CURSOR를 사용하여 REF_CURSOR를 저장한다.

사용법)
3. CallableStatement 받기
``CallableStatement cstmt=con.preparecall("{ call 프로시저명(바인드변수,,,) }");``

4. 바인드 변수 값 설정
in parameter

out parameter
``cstmtregisterOutParameter(인덱스, Types.REF_CURSOR);``

5. 프로시저 실행

6. out parameter에 저장된 값 받기
``ResultSet rs=(ResultSet)cstmt.getObject(인덱스);``