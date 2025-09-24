## Constraint(제약사항)
- 개발자가 원하는 값을 컬럼에 저장하기 위해서 사용하는 것
- primary key, foreign key, unique, not null, check, default(제약사항은 아니지만 같이 묶여서 본다, user_tab cols DD에서 확인)
- user_constraints DD에서 테이블에 설정된 제약사항을 확인할 수 있다.
- column단위 제약사항 또는 table 단위 제약사항으로 설정할 수 있다.
- alter를 사용해서 제약사항을 편집할 수 있다.

문법)
```sql
create table 테이블명(
 컬럼명 데이터형(크기) constraint 제약사항명 제약사항종류,
 컬럼명 데이터형(크기) constraint 제약사항명 제약사항종류,

 constraint 제약사항명 제약사항종류(적용컬럼명),
 constraint 제약사항명 제약사항종류(적용컬럼명),
);
```

### 컬럼단위 제약사항(column level constraint)
- 제약사항을 적용받을 컬럼 뒤에 선언하기 때문에 제약사항을 적용받을 컬럼명을 명시하지 않는다.
- 모든 제약사항을 설정할 수 있다.

### 테이블단위 제약사항(table level constraint)
- 컬럼의 선언이 모두 종료된 후 제약사항을 선언하기 때문에 제약사항을 적용받을 컬럼명을 명시한다.
- primary key, foreign key, unique, check만 사용가능

------------------------------------------------------------------------
### primary key(주키, 기본키)
- 테이블에 하나만 설정할 수 있다.
- 컬럼의 값이 null을 허용하지 않고, 유일해야 하는 경우
- 단일 컬럼으로 구성되는 경우도 있고, 복합 컬럼으로 구성될 수도 있다.
