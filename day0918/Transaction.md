## Transaction
- DB작업 단위
- DML중 insert, update, delete만 Transaction 대상 쿼리문
- 쿼리문 하나로 Transaction이 구성되는 경우도 있고, 여러 개의 쿼리문이 조합되어 Transaction이 구성되는 경우도 있다.
- DCL의 commit, rollback으로 Transaction을 처리
- transaction 완료: 모든 쿼리문이 성공한 경우
  commit: 접속자 세션에서 변경된 내용을 HDD에 기록, 변경된 내용을 모든 접속자 세션으로 통지하는 일.(모든 접속자 세션에서 변경된 레코드를 인지하고 사용한다.), 저장점이 사라진다, commit된 데이터는 rollback으로 작업 취소를 할 수 없다.
  
  사용법)
  ``commit;``

- transaction 취소: 쿼리문 중 하나라도 실패한 경우.(일관성을 보장하기 위해 모든 작업 취소)
  rollback: 접속자 세션에서 변경한 내용을 취소하는 것, savepoint와 함께 사용하면 특정 지점까지의 작업을 취소 시킬 수 있다.
  
  사용법)
  바로 전 commit 이후의 모든 transaction 대상 쿼리문의 작업을 취소시킨다.
  ``rollback;``
  
  savepoint 사용(특정 위치까지의 작업을 취소)
  ``rollback to 저장점명;``
  
  savepoint: transaction 대상 쿼리문을 작성하기 직전
   
  