## Network Programming
-C/S (Client/Server) Programming (통신 프로그램)
-java.net 패키지에서 관련 클래스들을 제공
-network: 서로 다른 컴퓨터를 연결하기 위한 데이터 통신망(컴퓨터가 제어하는 통신망)
-NIC(Network Interface Card): LAN카드
RJ-45와 UTP Cable로 Hub 연결(전송하는 데이터의 양에 따라서 두께가 달라진다. CAT.1~CAT.8)
컴퓨터에서 네트워크를 사용하기 위해 장착하는 카드(칩)
MAC주소가 할당-제조사 할당-유일: Hub에서 컴퓨터를 식별하기 위해 사용
ip address가 할당-사용자가 할당-네트워크에서 컴퓨터를 식별하기 위한 주소(IPv4, IPv6)

-Hub-여러개의 컴퓨터를 연결하고, 연결된 컴퓨터의 MAC주소로 컴퓨터를 찾아가기 위한 장비
-Router-여러 대의 Hub 관리, 목적지 컴퓨터의 최단거리를 테이블로 저장하고 관리하는 일
-Protocol-데이터를 송,수신하기 위한 전송규약

*java.net 패키지에서 관련 클래스를 제공
-TCP를 구현한 클래스: ServerSocket, Socket(소켓 통신)=>서버와 클라이언트의 역할이 명확하게 구분
-UDP를 구현한 클래스: DatagramPacket, DatagramSocket
=>서버와 클라이언트의 역할이 명확하게 구분되어 있지 않다.(네트워크에 먼저 참여한 super peer가 서버가 된다.)

서버의 사용법)

1.생성) -PORT를 열어서 서버실행
ServerSocket server=ServerSocket(포트);
PORT: 컴퓨터 들고 나는 문
0~65535까지 포트가 열릴 수 있다.
0~1024 이하의 포트는 이미 열려있는 경우가 많다.
가급적인 1025~65535 포트 연다.
PORT 선점(같은 프로그램일지라도 포트는 하나만 사용할 수 있다.)

2.접속자 소켓을 받는다.
Socket client=server.accept(); //접속자가 있으면 다음으로 진행

클라이언트의 사용법)

1.Socket 생성) -서버의 주소와 PORT 사용하여 생성-
(생성되자마자 ip의 서버에 포트로 접속시도)
Socket client=new Socket("서버ip", 서버포트);



### OSI 7 Layer Reference Model
-개방형 시스템에서 데이터를 주고 받는 것을 이해하기 쉽도록 정의한 7계층(실제 네트워크 구성 TCP/IP(4계층) 모델을 사용)
-상위계층은 하위계층으로 PDU(Protocol Data Unit)를 내려주고 서비스를 요청(Service Request)한다.

*응용 계층(Application Layer)
-사용자가 네트워크에 접속하기 위해 사용하는 프로그램(http, ftp, telnet, ssh)

*표현 계층(Presentation Layer)
-사용자가 입력한 값이 어떻게 변화되어 컴퓨터에게 보여질지를 설정하는 계층.
charset encoding, 암호화

*세션 계층(Session Layer)
-가상연결(호 단위 연결)

*전송 계층(Transport Layer)
-실제연결(Protocol - TCP,UTP)

*네트워크 계층(Network Layer)
-경로를 찾는 일(길찾기), Packet 시작점에서 최종 목적지까지 성공적으로 전달될 수 있도록 경로를 설정하는 일

*데이터링크 계층(DataLink Layer)
-데이터를 오류없이 전송하기 위해 전선선로(media)에 어떻게 link해줄지 설정하는 일

*물리 계층(Physical Layer)
-데이터를 물리적인 매체로 실제 매핑하여 보내는 일(비트 흐름 제어)

### 데이터 전송시 장애 원인(Transmission Impairment)
*장애 원인 3가지
-외부에서 발생하는 큰 충격
-데이터를 전송하는 회선에서 열이 발생 경우
-혼선

*패킷(데이터를 보내기 위한 정보를 싣는 단위)은 일반적으로 헤더, 데이터, 트레일러로 구성. 통신에 사용되는 프로토콜에 따라 다르다.
header-패킷 제어정보(출발지와 목적지 IP주소, port, 전송제어 정보 등 포함)
data-실제 전송하는 정보(예: 웹페이지 html코드, 이메일 본문 내용)
trailer-패킷 끝에 추가되는 부분. 패킷이 올바르게 전송되었는지 오류검사정보를 포함

-TCP 프로토콜은 데이터를 네트워크 상황에 따라 MTU가 가변적으로 결정되는 segment(패킷에 있는 정보가 포함)로 분할되어 전송된다.

*MTU(Maximum Transmission Unit)는 데이터 링크에서 전송할 최대 크기를 설정.
이더넷에서 최소 68byte~최대 1500byte까지 설정한다.
(Jumbo 프레임은 최대 9000byte MTU 설정 가능)

*Java언어에서는 OSI 7Layer의 상위 4계층에 해당하는 코딩을 한다. => 쉽다.
-응용계층: Application개발(JFC - Swing, Event Handling)
-표현계층: charset 설정(encoding, decoding)
-세션계층: 가상연결관리(소켓생성,close)
-전송계층: 프로토콜 선택(TCP,UDP)- Socket, Datagram

*TCP(Transmission Control Protocol)
-전화
-신뢰성 통신
-패킷의 크기가 고정 (1byte)
-오류 검출 가능
-속도가 느림
-데이터에 안정성이 요구되는 프로그램(결제, 웹 페이지 등 데이터가 반드시 전달되어야 하는 경우 사용)

*UDP(User Datagram Protocol)
-우편
-비신뢰성 통신
-패킷의 크기를 개발자가 변경할 수 있다.
-오류 검출 불가능
-속도가 빠름
-속도에 민감한 프로그램에서 사용(화면 공유, 화상 채팅)

