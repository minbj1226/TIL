# CLOB 데이터 얻기
- CLOB 컬럼은 별도으의 Stream을 붙여서 파일 얻어 온다.

1. clob 데이터 형 얻기
Clob clob=rs.getClob("컬럼명");

2. Clob 객체에서 스트림 얻기
Reader reader=clob.getCharacterStream(); //줄단위(\n)로 읽는 기능이 없다.

3. 줄 단위로 읽어 들일 수 있는 스트림 연결
BufferedReader br=new BufferedReader(reader);

4. 읽어 들이기
String temp="";
while( (temp=br.readLine()) != null) {
	temp;
}