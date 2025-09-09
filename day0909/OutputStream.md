## 출력스트림
*console 출력
*파일 출력
-JVM안에서 발생한 데이터를 HDD File로 출력
-8bit stream FileOutputStream, 16bit stream FileWriter가 제공
-스트림을 생성하면, 목적지에 파일 없으면 생성하고, 파일이 있으면 덮어 쓴다. 디렉토리는 생성할 수 없다=>File 사용

0.디렉토리 존재?
``File dir=new File("디렉토리);``
N=> 디렉토리 생성 dir.mkdirs()

1.파일이 존재하니?
``File file=new File(dir.getAbsolutePath()+File.separator+"파일명");``
Y=> 덮어쓸지 여부
n=> 생성

2.스트림 생성)파일이 없으면 생성하고, 있으면 덮어쓴다.
``FileOutputStream fos=new FileOutputStream(file);``

3.파일에 슬 내용을 스트림에 기록
``fow.write(정수);``

4.스트림에 기록된 내용을 목적지로 분출
``fow.flush()``
