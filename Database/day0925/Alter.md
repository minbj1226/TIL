## alter
- DDL
- 테이블 변경, 제약사항 변경, 계정 비번 변경, 계정 잠그기의 다양한 일을 할 수 있다.

### 계정비번 변경
- 모든 계정은 자신의 비번을 변경할 수 있다.
- 관리자는 모든 계정의 비번을 변경할 수 있다.
- 다음 번에 접속할 때 부터 적용

문법)
``alter user 계정명 identified by 비번``

### 계정 잠그기, 열기 - 관리자계정만 가능

문법)
``alter user 계정명 account lock;``
``alter user 계정명 account unlock;``

### 테이블 변경
- 컬럼명 변경
문법)
``alter table 테이블명 rename column 이전컬럼명 to 현재컬럼명;``

- 컬럼 추가
추가되는 컬럼은 테이블에 가장 마지막 컬럼으로만 추가된다.
문법)
``alter table 테이블명 add 컬럼명 데이터형(크기) 컬럼단위제약사항``

칼럼단위제약사항 <- 레코드의 존재유무에 따라 사용가능한 제약사항이 다르다.
레코드가 없다면 모든 제약사항을 추가할 수 있다.
레코드가 존재하면 null을 허용하는 제약사항만 추가될 수 있다.(foreign key, unique, default)

- 컬럼 삭제
문법)
``alter table 테이블명 drop column 컬럼명;``

- 컬럼 데이터형 변경
레코드가 존재: 동일 데이터형에서 크기만 변경.
레코드가 존재x: 데이터형 자체 변경
문법)
``alter table 테이블명 modify 컬럼명 데이터형(크기) 컬럼단위 제약사항;``

### 테이블명 변경

문법)
``alter table 테이블명 rename to 변경할테이블명``

*제약사항 관리
- 제약사항 추가: 테이블 단위 제약사항만 가능
문법)
``alter table 테이블명 add constraint 제약사항명 제약사항종류(적용컬럼명)``

- 제약사항 삭제
19c까지는 PK를 삭제하면 PK에 속해있는 not null조건은 삭제되지 않는다.
문법)
``alter table 테이블명 drop constraint 제약사항명``

- 제약사항 활성화, 비활성화
활성화: 레코드의 상태에 따라 제약사항에 위배되는 레코드가 없으면 활성화된다.
문법)
``alter table 테이블명 enable constraint 제약사항명``

비활성화
문법)
``alter table 테이블명 disable constraint 제약사항명``
