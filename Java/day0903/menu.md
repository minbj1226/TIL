Menu
==========
-프로그램에서 제공되는 기능들을 하나로 묶어서 사용자에게 제공하는 컴포넌트
-MenuBar, Menu, MenuItem으로 구성된다.

사용법)
1.JMenuBar생성(메뉴가 올라가는 바)
JMenuBar jmb=new JMenuBar();

2.Menu생성(메뉴아이템을 모아서 가지고 있는 버튼 종류)
JMenu jmFile=new JMenu("파일");
JMenu jmEdit=new JMenu("편집");

3.MenuItem생성
JMenuItem jmiNew=new JMenuItem("새글");
JMenuItem jmiOpen=new JMenuItem("열기");

4.MenuItem을 Menu에 배포
jmFile.add(jmiNew);
jmFile.add(jmiOpen);

메뉴 아이템 간 구분선 설정
메뉴객체.addSeperator();

5.Menu를 JMenuBar에 배포
jmb.add(jmFile);
jmb.add(jmEdit);

6.MenuBar를 Frame 설정
프레임.setMenubar(jmb);
