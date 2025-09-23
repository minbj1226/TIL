## C/S흐름

1.Server port 열기
(DOS: netstat.ext로 열린 포트를 확인)
ServerSocket server=new ServerSocket(65520);

2.Socket 생성
(자신 컴퓨터의 임의의 포트를 연 후 지정한 IP와 PORT로 연결을 시도)

*Socket과 ServerSocket은 컴퓨터끼리 연결을 수행, 데이터를 주고 받기위해서는 
IO Stream을 사용한다.

1.ServerSocket생성
``ServerSocket server=new ServerSocket(50000);``

2.Socket생성
``Socket client=Socket("서버ip",50000);``

3.접속자 소켓 받는다.(회선 확립)
``Socket client=server.accept();``

4.소켓에서 출력 스트림을 얻는다.
``DataOutputStream dos=New DataOutputStream(client.getOutputStream());``