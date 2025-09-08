## IO stream
- Java API에서 입력과 출력을 할 수 있는 클래스
- 단방향 Stream(읽기는 읽기만 가능, 쓰기는 쓰기만 가능)
- java.io 패키지에서 관련 클래스들을 제공
- 8bit stream(byte기반 스트림)-> 모든 종류의 데이터를 읽어 들이거나 쓸 수 있다.(파일복사), 
16bit stream(문자열 기반 스트림)-> 독자 포멧이 없는 문자열 데이터만 읽고 쓸 수 있다.(메모장으로 열리는 파일) 두 가지를 제공

### stream 상속도

flowchart TD
    A[8bit Stream (Byte)] --> B[InputStream]
    A --> C[OutputStream]

    B --> B1[FileInputStream]
    B --> B2[DataInputStream]
    B --> B3[ObjectInputStream]

    C --> C1[FileOutputStream]
    C --> C2[DataOutputStream]
    C --> C3[ObjectOutputStream]

    D[16bit Stream (Character)] --> E[Reader]
    D --> F[Writer]

    E --> E1[FileReader]
    F --> F1[FileWriter]
