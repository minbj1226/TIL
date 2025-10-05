## sequence
- 순차적으로 증가하는 번호를 저장하고 관리하는 객체
- user_sequences DD에서 생성된 시퀀스 정보를 확인할 수 있다.
- currval, nextval, pseudo column으로 시퀀스 객체가 가진 현재 변호 또는 다음 번호를 얻을 수 있다.
	- currval: 메모리(server instance)에 올라와 있는 시퀀스 객체의 현재 번호를 얻을 때
	- nextval: 시퀀스 객체의 다음 번호를 얻을 때
- Oracle 11g까지는 서버가 종료되면 cache에 저장된 번호가 사라지는 이슈가 있었음.

작성법)

생성)
```sql
create sequence 시퀀스명
increment by 증가값
start with 시작값
maxvalue 끝
cache 메모리에 올려놓을 번호 수
반복 여부
```

삭제)
``drop sequence 시퀀스명``

사용법)

현재번호)
접속자 세션에 시퀀스가 올라와있지 않으면 error 발생
시퀀스명.currval

다음번호)
시퀀스명.nextval 

1.접속자 세션에 올라와있는 시퀀스 객체가 올라와있니?
  Y: 시퀀스 객체의 cache가 모두 소진되었니?
  	Y: File 영역에 last number를 변경한 후
  	   접속자 세션에 시퀀스를 갱신하고 다음 번호를 얻는다.
  	N: 접속자 세션에 시퀀스번호를 다음 번호로 갱신한 후 번호를 얻는다.
  N: File 영역에 last number를 변경한 후, 접속자 세션에 시퀀스를 로딩하고 다음 번호를 얻는다.
  
 
  