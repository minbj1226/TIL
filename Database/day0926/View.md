## view
- 실제 테이블에서 도출되는 가상의 테이블
- 보안성 향상, 사용자 편의성 향상
View를 통한 접근	자주 사용되는 조건으로 view 만들고 접근, 조인을 한 상태로 view 만들고 접근
- user_views DD에서 확인 가능
- create view 권한이 있는 계정만 생성 가능.(dba_sys_privs 권한 확인 가능)
- 단순 view와 복합 view 두 가지로 생성할 수 있다.

단순 view
1. 테이블 하나로 도출 view
2. 함수, 연산식을 사용하지 않고 생성된 view
3. DML이 가능(insert, update, delete, select)

복합 view
1. 테이블 여러개를 사용하여 도출한 view
2. 함수, 연산식을 사용하여 생성된 vidw
3. DML이 불가능(insert-불가능, update,delete-상황에 따라 다르다, select-가능)

사용법)
권한 부여(관리자)
``grant create view to 계정명;``

권한 회수(관리자)
``revoke create view from 계정명;``

1. 생성)
``create view 뷰명(컬럼명,,,)as (select 컬럼명,,,) option``

option
- with readonly: 읽기 전용 view 생성
- with check option: view에 의해 검색된 레코드만 DML 가능

