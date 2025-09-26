## 테이블 결합
- union, join

### union
- 테이블을 수직으로 결합하여 검색할 때 사용
- 컬럼의 수, 데이터형이 일치해야한다.

union: 중복데이터를 보여주지 않는다.
union all: 중복데이터를 보여준다.

문법)
```sql
select 컬럼명,,,
from 테이블명
where
union [all]
select 컬럼명,,,
from
```

### join
- 서로 다른 테이블의 컬럼을 옆으로 붙여서 조회하는 것
- inner join, outer join, cross join, self join이 존재
- 조인조건을 잘못 설정하면 모든 레코드들이 곱해져서 조회되는 cartesian product 발생 (사용할 수 없는 조회 결과가 생성)
- ANSI문법, Oracle join 문법 두가지를 지원
- driving 테이블이 잘못 선정되면, 조인시간이 증가할 수 있다.

*inner join
- 서로 다른 테이블에서 동일 데이터가 존재하는 경우의 레코드만 검색하는 조인
- 한쪽 테이블에만 데이터가 존재하면 데이터가 조회되지 않는다.(모든 레코드를 검색할 수 없다.)
- 양쪽 테이블에 값이 동일하게 존재하는 레코드만 검색하는 join

ANSI 문법)
```sql
select 컬럼명,,,
from 테이블명
inner join 조인할 테이블명
on 조인조건
inner join 조인할 테이블명
on 조인조건

where 검색조건
```

조인할 테이블에 모든 칼럼명을 정의
테이블이 다르고 컬럼명이 같다면 error
=>테이블명.컬럼명

테이블에 alias가 사용되면
=>alias.컬럼명

ORACLE 문법)
```sql
select 컬럼명,테이블명.컬럼명, alias명.컬럼명
from 테이블명 alias, 조인할 테이블명 alias, 조인할 테이블명 alias,,,
where 조인조건 and 검색조건
```

### driving table
- 조인할 때 키가 되는 테이블

*driving table 선정 기준
- 관계가 있는 테이블에서는 PK컬럼을 가진 테이블이 되는 것이 좋다.
- 관계가 없는 테이블에서는 레코드의 수가 적거나, 컬럼의 값이 다양성이 적은 테이블이 되는 것이 좋다.

### outer join
- 한쪽 테이블에만 레코드가 존재하더라도 조회가 가능한 조인
- ANSI 문법(left, right, full), 
Oracle 문법(left, right => full outer join 없다)

문법)
```sql
select 		   컬럼명,테이블명.컬럼명,alias명.컬럼명
from 		   테이블명 alias
종류 outer join 조인할 테이블명 alias
on			   조인조건
```

- Oracle 문법
- 조인 조건에 (+)를 사용한다.
- 레코드가 존재하지 않는 컬럼에 (+)를 사용한다.
- 양쪽엔 (+) 붙일 수는 없다.

문법)
```sql
select
from 테이블명 alias, 조인할 테이블명 alias,,,
where 조인조건(alias 컬럼명(+) = alias.컬럼명)
```

### self join
- 테이블 하나를 조인하는 것
- Non-EQUI join 유형으로 사용
- 조회용도의 목적을 가진 테이블과 조건용도의 목적을 가진 테이블로 구분하여 사용

문법)
```sql
select 
from 테이블명 alias, 조인할 테이블 alias
where
```

앞 테이블은 조회용으로 사용
- select 조회컬럼에만 사용
- 조건에 비교를 당할 때

뒤 조인할 테이블은 조건용으로 사용
- 조인할 조건에 사용
- 검색할 조건에만 사용
- 조회컬럼에 사용되면 조건에 일치하는 동일한 값만 조회된다.

ex)
--사원테이블에서 사원명이 'SCOTT'인 사원보다 연봉을 많이 받는 사원에 사원번호, 사원명, 연봉, 입사일을 조회
```sql
select e.empno, e.ename, e.sal, e.hiredate
from emp e, emp e2
where (e.sal>e2.sal) and e2.name='SCOTT';
```