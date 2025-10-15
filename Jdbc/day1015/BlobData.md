# BLOB 데이터 얻기
- BLOB 컬럼은 별도의 Stream을 붙여서 파일을 얻어 온다.

1. 입력스트림 얻기(DB에서 파일 꺼내기 위함)<br>
``InputStream is=rs.getBinaryStream("컬럼명");``

2. 읽어들인 내용을 파일로 출력하기 위해서 출력 스트림 생성<br>
```Java
File file=new File("저장할 파일의 경로");
FileOutputStream fos=new FileOutputStream(file);
```

3. 입력스트림으로 부터 읽어들인 파일을 출력스트림을 통해 목적지로 분출<br>
```Java
byte[] readData=new byte[512];
int byteLength=0;

while( (byteLength=is.read(readData)) != -1) {
	fos.write(readData, 0, dataLength);
}
fos.flush();
```

4. 스트림 종료(Connection을 끊기전에 끊는다.)<br>
``is.close(); fos.close();``