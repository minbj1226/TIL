# FileDialog
-파일을 열거나, 저장할 component
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
-부모창에서 제공할 수 없는 부가적인 정보를 제공하기 위한 Window Component
-java.awt.Dialog(부모 윈도우가 존재해야만 제공) , javax.swing.JDialog(부모 윈도우가 존재하지 않아도 제공)가 제공

사용법)
1.생성
JDialog jd=new Jdialog(부모윈도우, "타이틀바 메시지", 모달여부);
모달여부-true:모달(부모창이 선택x), false:비모달(부모창 선택O)

```
public class SubWin extends JDialog{
	public SubWin(JFrame 부모){
		super(부모, "타이틀바 메시지", modal);
	}
}
```
2.컴포넌트를 생성 배치) BorderLayout 기본 Layout
jd.add("위치", 컴포넌트);

3.크기 설정

4.가시화

5.종료처리
```
setDefaultCloseOperation(JDialog.DISPOSE_ON_CLOSE);
```