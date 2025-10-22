# Trigger
- 특정 테이블에서 DML 작업이 수행될 때 자동으로 실행되는 PL/SQL의 객체
- 연쇄 작업 수행
- user_trigggers DD에서 확인
- trigger 안에서는 commit, rollback을 할 수 없다. 대상 테이블에서 트랜잭션이 완료될 때 함께 수행된다.
- 트리거의 동작은 행 단위와 쿼리문 단위로 실행 시킬 수 있다.

* 대상 테이블의 실행 시점을 기준으로 before trigger(감시 테이블에서 DML이 발생하기 전에 실행되는 Trigger),after trigger(감시 테이블에서 DML이 발생한 이후에 실행되는 Trigger) 존재<br>

작성법)
```SQL
create or replace trigger 트리거명
시점기준 감시할 DML문 on 감시할 테이블명
트리거 레벨

begin
	연쇄적으로 작업할 쿼리문
end;
/
```

연쇄적으로 작업할 쿼리문: 감시하는 테이블에서 사용된 값들을 사용할 수 있다.

* insert: new.컬럼명(이전에 값은 없고, 새로운 값만 존재)
* update: new.컬럼명(새로 변경된 값), old.컬럼명(변경되기 전 값)
* delete: old.컬럼명(새로운 값 없다.)

작성법)
```SQL
create or replace trigger 트리거명
after insert or update or delete on 테이블명
for each row

begin
	연쇄적으로 동작할 쿼리문
	
end;
/
```

## 행 단위 Trigger
- 감시테이블에서 DML로 인해 변경된 각 행(row)에 대해서 trigger를 실행 (row level trigger)

## 쿼리문 단위 Trigger
- DML 문장이 끝나면 한번만 실행되는 trigger (statement level trigger)
