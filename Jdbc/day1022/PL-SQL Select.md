# PL/SQL에서 select
- PL/SQL에서 insert, update, delete는 SQL문법과 동일하다. select은 검색 결과를 변수에 저장하는 into절 필요.
- PL/SQL내에서 select 반드시 한 행만 조회되어야한다.
0행 검색 - error, n행 검색 - error

문법)
```SQL
select 컬럼명
into 변수명
from 테이블명
where 조건
```

- 실제 테이블의 데이터 형과 크기를 참조하여 변수를 선언할 수 있다.
문법)
- 컬럼하나 참조:``%type``

변수명 테이블명.컬럼명%type

empno emp.empno%type; -> number(4)

- 테이블의 모든 컬럼을 참조:``%rowtype``

변수명 테이블명%rowtype

emp emp%rowtype;

사용법) 변수명.컬럼명 =?