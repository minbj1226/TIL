## non-unique index
- 컬럼의 값이 중복 될때 사용하는 인덱스(일반 컬럼에 주로 적용)
- 개발자가 주로 수동으로 생성하는 index

문법)
``create index 인덱스명 on 테이블명 (컬럼명 asc);`

## bitmap index
- 컬럼의 값이 중복되긴하나 독특한 코드 형태의 값일 때 사용하는 인덱스

문법)
``create bitmap index 인덱스명 on 테이블명 (컬럼명);``

## composite index
- 여러 개의 컬럼으로 인덱스가 구성되어야 할 때
- unique index 계열(여러 개의 컬럼에 동일한 값이 추가되면 ERROR 발생)

문법)
``create unique index 인덱스명 on 테이블명(컬럼명,,,,);``

## index hint
- 인덱스가 적용된 컬럼을 사용하여 작업을 할 때 사용
- 인덱스를 사용한 정렬을 수행
- 인덱스를 적용한 컬럼을 사용하여 검색을 하면(검색조건에 인덱스 컬럼이 사용되면) 
빠르게 검색, 정렬할 수 있다.
- index를 생성하면 지정한 컬럼에 asc으로 기본 정렬된 인덱스가 생성된 create[unique]
index 인덱스명 on 테이블명(컬럼명); 
- index를 설정한 후 index hint를 사용하면 정렬을 수행할 수 있다.
(index가 설정된 컬럼은 order by해도 괜찮다.)

사용법)
조회 컬럼에 /*+ */ 또는 --+로 인덱스 힌트를 사용할 수 있다.

- 인덱스를 사용한 오름차순정렬 (인덱스를 asc로 생성)

select /*+ index (테이블명 인덱스명)*/ 컬럼명,,,
where 절 포함

- 인덱스를 사용한 내림차순정렬 
select /*+ index desc (테이블명 인덱스명)*/ 컬럼명,,,
where 절 포함

index가 desc로 생성되면 desc+desc=asc
hint를 desc로 설정하면 asc로 검색할 수 있다.

index가 asc로 생성되면 hint를 desc로 사용했을 desc된 데이터를 검색할 수 있다.

주의: 인덱스 컬럼을 함수로 사용하면 index가 사용되지 않는다.