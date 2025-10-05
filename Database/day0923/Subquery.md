## Subquery(하위 질의)
- query문안에 select query문을 정의하는 문법
- 단수행 subquery(서브쿼리의 조회 결과가 한 행이 나오는 서브쿼리), 
복수행 subquery(서브쿼리의 조회 결과가 여러 행이 나오는 서브쿼리) 두 가지를 지원
- 조회 결과를 사용하여, 쿼리문(create, insert, update, delete, select)을 실행해야할 때
- create, insert, update, delete, select에서 사용할 수 있다.

### create subquery
- 테이블을 복사할 때 사용
- 단수행, 복수행 서브쿼리를 사용할 수 있다.
- 원본 테이블에 설정되어 있는 제약사항(primary key, foreign key, unique)은 복사되지 않는다.
- 조회쿼리(서브쿼리)에 사용되는 컬럼명, 데이터형, 크기, 레코드 그대로 복사된다.
- 제약사항 중 not null 조건은 복사된다.

문법)
``create table 테이블명 as (select,,,)``

subquery에서 조회된 결과를 inline view라고 한다.
inline view를 사용하여 테이블을 생성한다.

### insert subquery
- 다른 컬럼의 값을 사용하여 레코드를 추가할 때
- 단수행, 복수행 서브쿼리 모두 사용가능

-단수행 문법)
``insert into 테이블명(컬럼명,,) values(값, (select 컬럼명 from 테이블명 where),,,)``

-복수행 문법)
``insert into 테이블명(컬럼명,,,) (select ,,,)``
조회된 여러행을 추가할 때 사용  
조회되는 컬럼의 수와 insert 컬럼 수, 데이터 형은 반드시 일치해야 한다.

### update subquery
- 단수행 서브쿼리만 가능
- 다른 컬럼의 값으로 변경할 때
- where 절에서 in을 사용하는 경우에는 복수행 서브쿼리도 사용 가능

문법)
```
update 테이블명
set 컬럼명=(select 컬럼명,,,)
where 컬럼명=(select 컬럼명,,,)
```

### delete subquery
- 단수행 서브쿼리만 가능
- 다른 컬럼의 값으로 삭제할 때
- where절에서 in을 사용하는 경우에는 복수행 서브쿼리도 사용 가능

문법)
```
delete from 테이블명
where 컬럼명=(select 컬럼명,,,)
```

### select subquery
- 단수행, 복수행, scalar subquery를 지원
- 다른 컬럼의 값으로 조회를 해야할 때

단수행 서브쿼리)
where절에서 사용

select 컬럼명, 함수(컬럼명), 컬럼명 alias, 컬럼명 연산자
from 테이블명
where 컬럼명=(select ,,,)

### scalar subquery
- 조회하는 컬럼에 사용하는 subquery
- scalar subquery 바깥 테이블에 존재하는 값을 참조하여 실행되기 때문에 단독으로 실행될 수 없다.
- 테이블명은 다르고 컬럼명이 같다면 컬럼을 식별하기 위해서 "테이블명.컬럼명"의 문법을 사용한다.
- 단수행 서브쿼리만 가능.

문법)
```
select 컬럼명,,,(select 컬럼명 from 테이블명 where 컬럼명=조건)
from 테이블명
```

### 복수행 서브쿼리
- 안쪽 쿼리문의 조회결과(inline view)를 사용하여 재조회하는 것
- 바깥 쿼리문은 실제 테이블을 조회하는 것이 아닌 조회결과(inline view)를 사용한 조회이기 때문에 안쪽 테이블에서 alias를 사용하면, 바깥 쿼리문에서는 alias가 컬럼명으로 인식된다.
- 바깥 쿼리문은 안쪽 쿼리문에서 조회된 컬럼만 사용될 수 있다.
<<<<<<< HEAD
- 많은 양의 레코드에서 일부분의 레코드를 잘라서 조회해야 할 때

### rownum
- 조회되는 레코드에 순차적인 번호를 부여하는 가상 컬럼
- rownum을 where절에서 사용하면 시작 값이 1에서부터는 검색이 되나, 1번을 초과하면 검색이 되지 않는다.
- 모든 select마다 따로 생성되고 사용된다.
- order by 절과 함께 사용하면 번호가 섞인다.
=======
- 많은 양의 레코드에서 일부분의 레코드를 잘라서 조회해야 할 때
>>>>>>> branch 'main' of https://github.com/minbj1226/TIL
