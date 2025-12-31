# Procedure
- 자주 사용될 쿼리문이나 업무로직을 미리 만들어두고, 필요한 곳에서 사용하기 위해

## Procedure 작성법
```
create or replace procedure 프로시저명(매개변수 타입 데이터형,,,)
is
--변수 선언, cursor 선언, record 선언, table 선언
begin
--업무 로직을 처리(연산, 제어, 쿼리문)
exception
--예외처리 코드
end;
```

- 컴파일: @경로/파일명.sql
- 실행:
bind변수 선언
var변수명 데이터형(크기)
간접실행(실행기:execute, exec)
exec 프로시저명(값,,,변수명)
값 출력
print 변수명

## MyBatis procedure 호출
- `<select>`만 사용
- `<select>`안에서 쿼리문 실행이 아닌 Procedure를 호출할 수 있도록 모드를 변경해준다.

사용 예)

```
<select id="아이디" parameterType="" statementType="CALLABLE">
{call 프로시저명(#{getter명, mode=파라메터종류, jdbcType=java.sql.Type의 데이터형}, ?, ?, ?)}
</select>

Cstmt=con.prepareCall("{call 프로시저명(?, ?, ?, ?, ?)}")
```

## select procedure
- cursor 사용(SYS_REFCURSOR 사용-커서의 제어권을 넘겨주는 커서)
- 암시적 커서(sql)
	- insert, update, delete의 수행 행수를 반환하는 커서
	- 개발자가 커서를 선언하지 않고, 쿼리문이 실행되면서 자동으로 생성되는 커서
	- 커서명은 SQL이고, 속성 %ROWCOUNT만 존재
- 명시적 커서
	- 여러 행을 조회할 때 사용하는 커서(PL/SQL에 select은 한행만 조회 가능)
	- 개발자가 커서를 선언하고 사용하는 커서
	- 프로시저 안에서 여러 행을 조회하는 커서와 제어권을 반환하는 커서 두가지를 제공
