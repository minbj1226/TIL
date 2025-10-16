# Transaction이 여러개의 쿼리문으로 구성될 때 처리
- Transaction 대상쿼리 => insert,update,delete
- 구성된 모든 쿼리문이 정상적으로 수행되었다면 commit으로 transaction을 완료해야하고 구성된 쿼리문 중 하나라도 실패하면 모든 작업을 rollback으로 취소해야한다.(transaction은 일관성 있어야 한다.)
- 쿼리문이 하나로 구성되는 경우에는 auto commit을 하는 것이 편하다.(java.sql.Connection은 autocommit이 기본설정으로 되어있다.)

사용법)
1.auto commit 해제
``con.setAutoConnection(false);``<- True: auto commit 설정, False: auto commit 해제

2.Connection을 class field에 선언(Connection이 정상적으로 close()되면 commit이 된다.)
*주의: 쿼리문을 수행하는 method안에서는 con을 close하지 않는다.

3.쿼리문을 수행하는 method 작성하고 반환형으로 쿼리문이 수행한 행 수를 반환.
Connection con;

```Java
public int db업무method() throws SQLException{
	int 행수 저장=쿼리문 1번 method();
	int 행수 저장=쿼리문 2번 method();
	
	return 1번 쿼리와 2번 쿼리를 수행한 행수를 합산 반환 
} 
```

4. 호출하는 곳에서 개발자가 목표로한 행수인지를 비교하여 commit, rollback 수행

public void useMethod(){
	int 수행된행수=db업무 method();
	
	if(수행된 행수==목표로 한 행수) {
		con.commit();
	} else{
		con.rollback();
	}
}