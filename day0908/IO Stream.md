## IO stream
- Java API에서 입력과 출력을 할 수 있는 클래스
- 단방향 Stream(읽기는 읽기만 가능, 쓰기는 쓰기만 가능)
- java.io 패키지에서 관련 클래스들을 제공
- 8bit stream(byte기반 스트림)-> 모든 종류의 데이터를 읽어 들이거나 쓸 수 있다.(파일복사), 
16bit stream(문자열 기반 스트림)-> 독자 포멧이 없는 문자열 데이터만 읽고 쓸 수 있다.(메모장으로 열리는 파일) 두 가지를 제공

### stream 상속도

8bit stream(한번에 움직이는 데이터의 양은 적지만 속도가 빠르다): 모든 데이터를 읽기 위한 스트림

16bit stream(한번에 움직이는 데이터 양은 많지만 속도가 느리다): 문자열 데이터를 읽기 위한 스트림

```Java I/O Streams
├─ 8bit Stream (Byte)
│ ├─ InputStream
│ │ ├─ FileInputStream
│ │ ├─ DataInputStream
│ │ └─ ObjectInputStream
│ └─ OutputStream
│ ├─ FileOutputStream
│ ├─ DataOutputStream
│ └─ ObjectOutputStream
└─ 16bit Stream (Character)
├─ Reader
│ └─ FileReader
└─ Writer
└─ FileWriter