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