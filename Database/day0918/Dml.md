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

### alias
- 컬럼명 또는 테이블 명 뒤에 정의할 수 있다.
- 컬럼명의 별명, 테이블 명 별명을 부여할 때
- 가독성 향상
- alias를 사용하면 조회결과에 나오는 컬럼명이 alias로 변경되어 나온다.
- select에 바로 연결되어 있는 where절에는 alias명을 사용할 수 없다.
- alias를 사용하면 컬럼명이나 테이블명을 대소문자 구분하여 생성할 수 있다.

문법)SQL
```
컬럼명 as(생략 가능) alias명
```

```
select 컬럼명 alias
from 테이블명
where alias를 사용할 수 없고, alias의 실제 컬럼명은 가능
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