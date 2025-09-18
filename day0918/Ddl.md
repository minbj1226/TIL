## truncate
- 테이블에서 모든 레코드를 절삭할 때 사용하는 DDL
- Transaction 대상쿼리가 아님(commit 하지 않아도 된다. - rollback 되지 않는다.)
- delete보다 속도가 빠르다.
- 특정레코드만 자를 수 없다.

문법)
```
truncate table 테이블명;
```

## drop
- DBMS의 모든 객체를 삭제할 때 사용하는 DDL
- oracle 11g부터는 삭제된 테이블은 휴지통으로 이동한다.
- 휴지통에 들어간 테이블은 복구 가능

문법)
```
drop table 테이블명;
```