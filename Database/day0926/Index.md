## index
- 레코드의 양이 많을 때 빠르게 검색하기 위해 제공하는 객체 (CPU Cost와 IO Cost가 줄어든다.)
- 자동 인덱스, 수동 인덱스 두 가지를 제공

자동 인덱스: 테이블을 생성할 때 PK, unique를 설정하면 자동으로 생성되는 index
수동 인덱스: 개발자가 필요에 의해 생성되는 index

- 모든 계정은 인덱스를 생성하고, 사용할 수 있다.
- 인덱스는 시간이 지날수록 실제 테이블의 레코드와 차이가 발생한다.(rebuild 해야한다.)
- 모든 레코드는 레코드를 식별하기 위해서 주소(rowid)를 가진다.
- user_indexes DD에서 생성된 index를 확인할 수 있다.
- user_ind_columns DD에서는 인덱스 설정된 컬럼을 확인할 수 있다.

ex)
AAATo	NAA		HAAAASr	AAA
데이터번호	파일번호	블록번호	레코드 번호 

인덱스 생성)
``create [인덱스 종류] index 인덱스명 on 테이블명(컬럼명,,,);``

*unique index
- 컬럼의 값이 유일할 때 사용하는 인덱스
- 테이블 생성시 primary key나 unique 제약사항을 설정하면 자동으로 생성(자동 인덱스)
- 개발자가 컬럼의 값이 유일할 때 수동생성도 가능

작성법)
```sql
create unique index 인덱스명 on 테이블명(컬럼명)
```

인덱스 삭제)
``drop index 인덱스명;``

### index rebuild
인덱스는 테이블에서 생성되는 객체이나, 테이블과는 별도의 동작을 수행한다.
시간이 지날수록 테이블은 변경 (insert,update,delete)되나 index는 변경되지 않는다.
일정주기를 가지고 index를 rebuild 하여 실제 테이블과 인덱스간의 격차를 줄여야한다. 

``alter index 인덱스명 rebuild;``

