Border
==================
-컴포넌트들을 묶어서 보여줄 때
-javax.swing.border 패키지에서 Border 클래스들을 제공

사용법)
1.컴포넌트 생성) 주로 Container Component에서 사용.
JButton jbtn=new JButton("버튼");

JPanel jp=new JPanel();
jp.add(jbtn);

2.Border 설정
-생성)
TitledBorder tb=new TitleBorder("타이틀");
LineBorder lb=new LineBorder(Color객체);

-컴포넌트에 설정)
jbtn.setBorder(tb);//일반 컴포넌트도 설정 가능
jp.setBorder(tb); //컨테이너 컴포넌트도 설정 가능