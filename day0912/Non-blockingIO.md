##NIO(Non-blocking I/O)
-JDK 1.4부터 도입된 패키지(JDK1.7에서부터 많은 기능 추가되었음)
-비동기적인 입.출력을 제공하는 클래스
-기존의 I/O보다 효율적인 다중 연결과 대용량 데이터(Gbyte 이상의 파일을 처리할 때 사용, 물리적인 Memory보다 큰 파일을 처리)를 처리할 때 사용
-N I/O의 핵심 구성 요소는 Channel(입,출력의 소스(파일, 네트워크)), Buffer(데이터를 임시로 저장하는데 사용)가 있다.
-비동기성(Asynchronous): 입,출력이(작업)이 완료될 때까지 기다리지 않고 다른 작업을 수행하는 것(속도 향상)
-채널을 통해서 입,출력이 일어나고, 데이터는 버퍼를 통해서 전송된다.

###대용량 텍스트 파일 읽기
-java.nio.file Path,Paths,Files 객체 사용

1.내용을 읽어들일 텍스트 파일을 선택
//JDK1.7 이상의 문법(Paths를 사용하여 Path를 얻기)
Path path=Paths.get("파일경로");

//JDK11 이상의 문법(Path 인터페이스를 사용하여 Path 얻기)
Path path=Path.of("파일경로");

2.Files 클래스를 사용하여 모든 내용을 줄 단위로 읽어 들일 수 있다.
List<String> allLines=Files.readAllLines(path).

3.반복
for(String line:allLines){
	line //읽어들인 모든행을 출력할 수 있다.
}

###NIO를 사용한 파일 복사