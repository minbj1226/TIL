# FileDialog
-파일을 열거나, 저장할 
-java.awt에서 제공
-OS에서 제공하는 FileDialog를 사용하는 클래스

사용법)
1. 생성
FileDialog fd=new FileDialog(부모컴포넌트, "타이틀바에 들어갈 내용", 모드);

2. 사용자에게 보여주기
fd.setVisible(true);

3. method 호출
-선택한 디렉토리 얻기
String dir=fd.getDirectory();
-선택한 파일명 얻기
String file=fd.getFile();

# JFileChooser
-javax.swing 패키지에서 제공하는 Component
-부모 Window가 없어도 제공할 수 있다.

사용법)
1.생성
JFileChooser jfc=new JFileChooser();
2.보여주기
jfc.showOpenDialog(부모컴포넌트);
jfc.showSaveDialog(부모컴포넌트);

# Dialog
-부모창(Frame)에서 뜨는 자식창(Dialog)