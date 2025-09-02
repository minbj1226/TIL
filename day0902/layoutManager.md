Layout Manager(배치 관리자)
====================================
-Window Component, Container Component는 컴포넌트들을 손쉽게
배치하기 위해 배치관리자를 지원
-non-visual component
-자동배치관리자, 수동배치관리자 두 가지를 제공
-BorderLayout, FlowLayout, CardLayout, GridLayout, GridBagLayout
-사용: setLayout(사용할레이아웃객체)

*BorderLayout(경계레이아웃)
-----------------------
-테두리 레이아웃
-Window Component의 기본 레이아웃
-하나의 영역에는 하나의 컴포넌트만 배치
-배치되는 컴포넌트는 고유크기를 무시하고 배치되는 영역에 크기 맞게 늘어남

사용법) 
1. Layout 매니저 생성
BorderLayout bl=new BorderLayout();

2. 레이아웃의 필요한 컴포넌트(Window, Container component)에 적용
setLayout(bl);

3. 원하는 위치에 컴포넌트를 배치
배치되는 영역을 생략: Center에 배치 -> add(컴포넌트)
배치되는 영역을 기술: 원하는 위치에 배치 -> add(배치위치, 컴포넌트)
원하는 위치에 배치하는 방법
문자열 상수-add("North", 컴포넌트);
BorderLayout에 Constant 사용-add(BorderLayout.NORTH, 컴포넌트);

*FlowLayout(흐름 레이아웃)
-Contatiner Component의 기본 레이아웃(Jpanel, JScrollPane)
-배치되는 컴포넌트는 자신의 고유크기를 유지
-윈도우 컴포넌트를 늘리거나 줄이면 배치된 컴포넌트들이 위->아래로 흐름
-배치하는 순서대로 L->R 진행하면서 컴포넌트들이 배치

사용법)
1. 배치관리자를 생성+적용
setLayout(new FlowLayout());

2. 컴포넌트 배치
add(컴포넌트);

*GridLayout(격자 레이아웃)
---------------------------
-행과 열로 구성된 레이아웃
-배치되는 컴포넌트는 고유크기가 무시되고, 배치되는 곳의 크기에 맞게 설정(모든 컴포넌트의 크기가 일정)
-각 영역에는 하나의 컴포넌트만 배치
-배치되는 순서는 L->R으로 배치
-설정한 행과 열의 수가 배치하는 컴포넌트의 개수와 맞지 않으면 JVM이 자동으로 배치를 수행

사용법)
1. 배치관리자 생성+적용
setLayout(new GridLayout(행, 열));
setLayout(new GridLayout(2,3));

2. 컴포넌트를 배치
add(컴포넌트);

*CardLayout
----------------------------------
-Container Component에만 적용 가능한 Layout
-한정적인 공간을 효율적으로 사용하기 위해서 고안된 Layout
-이벤트가 발생 되었을 때 CardLayout이 적용된 Contatiner Component를 변경하며 보여준다.

*GridBagLayout
------------------------------------------
-행과 열로 구성된 레이아웃
-행마다 높이도 다르고, 행마다 배치하는 컴포넌트의 수가 다를 때 사용하는 Layout

*수동배치(Absolute Positioning)
------------------------------------------
-배치관리자를 사용하지 않고, 개발자가 컴포넌트의 크기와 절대좌표를 사용한 배치 위치를 직접 정의하여 배치하는 방법
-정교한 디자인이 가능

문법)
1. 설정된 배치관리자를 해제
setLayout(null);

2. 컴포넌트 생성
JButton jbtn = new JButton("버튼");

3. 컴포넌트 크기 설정
jbtn.setSize(넓이, 높이);

4. 컴포넌트의 배치위치 설정
jbtn.setLocation(x좌표, y좌표);

5. 배치
add(컴포넌트);