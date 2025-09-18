## Select
- 테이블에서 모든 레코드의 특정 컬럼을 검색하는 DML(DQL)

문법)
``` 
select 컬럼명,,함수명(컬럼명),컬럼명 연산자,컬럼명 alias
from 테이블명

where절 검색조건

group by절 그룹으로 묶을 컬럼명
having절 그룹으로 묶을 조건
 
order by 정렬한 컬럼명
```

## Update
- DML중 하나
- Transaction 대상쿼리(commit, rollback)
- 최소 0건에서부터 최대 조건에 맞는 모든 레코드를 변경한다.

문법)
```
update 테이블명
set 컬럼명=변경할 값,,,

where절 컬럼명=기준값
```

## Delete
- DML중 하나
- Transaction 대상쿼리(commit, rollback)
- 최소 0건에서부터 최대 조건에 맞는 모든레코드(n건)을 삭제한다.

문법)
```
delete from 테이블명

where절 컬럼명=기준값
```