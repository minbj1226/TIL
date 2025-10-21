# CallableStatement를 사용한 Procedure의 실행

3. CallableStatement 얻기

CallableStatement cstmt=con.prepareCall("{call 프로시저명(자바 바인드 변수,,,)}");

자바 바인드 변수
- in parameter: 외부의 값을 procedure 내부로 전달
- out parameter: procedure 내부의 값을 외부로 전달

4. Bind 변수에 값 할당
- in parameter: 부모인 PreparedStatement에서 제공하는 method 사용
cstmt.setInt(인덱스, 값); cstmt.setString(인덱스, 값);

- out parameter: SQLPlus에서 실행할 때 var로 선언하는 bind 변수가 필요
=>java에서는 bind변수를 처리할 수 있는 method 제공.

cstmt.registerOutParameter(인덱스, Types 데이터형) <- 정수: Types.NUMERIC, 문자열: Types.VARCHAR

5. 프로시저 실행(method가 없다. => 부모인 PreparedStatement 제공하는 method 사용)
``cstmt.execute();``

* out parameter에 procedure가 실행한 결과가 저장된다.

6. Out parameter에 저장된 값을 받는다.
``int i=cstmt.getInt(인덱스);``
``String s=cstmt.getString(인덱스);``

- 프로시저에서 bind변수에 SYS_REFCURSOR 데이터 형을 사용하면 (select 쿼리 실행)
cstmt에서 getObject() 받고 ResultSet로 Casting하여 처리한다.
Object 변수명=cstmt.getObject(); //cursor가 반환
Result rs=(ResultSet)변수명;

## PL/SQL 내에서 DML(insert,update,delete,select) 사용
- auto commit이 되지 않는다.
- commit이나 rollback을 개발자가 직접 해야한다.
 -- 암시적 커서를 사용하여 쿼리문이 실행한 행의 수를 얻는다.
 -- PL/SQL에 암시적 커서
 - insert, update, delete 쿼리문이 실행되면, 실행된 행수를 얻는 cursor가 제공된다.
 - 자동으로 생성된다.