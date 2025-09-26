## sequence
- 순차적으로 증가하는 번호를 저장하고 관리하는 객체
- user_sequences DD에서 생성된 시퀀스 정보를 확인할 수 있다.
- currval, nextval, pseudo column으로 시퀀스 객체가 가진 현재 변호 또는 다음 번호를 얻을 수 있다.
 - currval: 메모리(server instance)에 올라와 있는 시퀀스 객체의 현재 번호를 얻을 때
 - nextval: 시퀀스 객체의 다음 번호를 얻을 때
- Oracle 11g까지는 서버가 종료되면 cache에 저장된 번호가 사라지는 이슈가 있었음.
