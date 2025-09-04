Event Handling
=================
-디자인에서 사용자의 동작이 있을 때, 그에 대한 대비코드를 준비해두고 실행하는 것
-event는 java.awt.event 패키지와 javax.swing.event 패키지에서 관련 인터페이스와 클래스를 제공

*이벤트의 종류
|사용자 동작|발생하는 이벤트|이벤트 Listener|컴포넌트를 이벤트 등록 method|사용 예
|--------|----------|-------------|----------------------|------
|클릭,엔터|ActionEvent|ActionListener|addActionListener(리스너를 구현한 객체)|JButton jbtn=new Jbutton("버튼");
																	 -is a
																	 jbtn.addActionListener(this)
																	 -Has a
																	 jbtn.addActionListener(이벤트처리객체)
|아이템 변경|ItemEvent|ItemListener|addItemListener(리스너를 구현한 객체)|JcomboBox jcb=new JcomboBox();
																 jcb.addItemListener(this)
																 jcb.addItemListener(이벤트처리객체)
|키보드의 키|KeyEvent|KeyListener|addKeyListener(리스너를 구현한 객체)|JTextComponenet의 하위 클래스
															  JTextField jtf=new JTextField();
															  jtf.addKeyListener(this)
															  jtf.addKeyListener(이벤트처리객체)
|윈도우 메뉴 키가 눌렸을 때|WindowEvent|WindowEventListener|WindowEventListener(리스너를 구현한 객체)|JFrame.Jdialog
																						 객체.addWindowListener(this)
																						 객체.addWindowListener(이벤트처리객체)
|마우스|MouseEvent|MouseListener|addMouseListener(리스너를 구현한 객체)|마우스를 클릭할 수 있는 모든 컴포넌트들
																addMouseListener(this);
																
																
처리순서)
컴포넌트를 이벤트 등록 > 사용자가 동작을 수행하면 > JVM이 이벤트를 발생 > 이벤트 Listener가 이벤트를 받고 > 정해진 코드를 수행																						 