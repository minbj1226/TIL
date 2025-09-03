Font
===========
-Non-Visual Component: 눈에 보이지 않는 Component.
-대상 컴포넌트에 글꼴, 스타일, 크기를 변경할 때 사용하는 컴포넌트.
-java.awt.Font 클래스를 사용

사용법)
1.Font class 생성
Font(String name, int style, int size)
name:글꼴
style:글꼴 스타일
size:글꼴 크기

2.컴포넌트 생성
컴포넌트 객체명=new 컴포넌트("라벨");

3.컴포넌트에 폰트를 적용(Jcomponent의 모든 하위 클래스는 글꼴을 설정할 수 있다.)
객체명.setFont(폰트객체);

*색변경
--------------
-색을 사용할 수 있는 java.awt.Color 사용
-Constant 사용, 생성자 사용
Constant: 제공되는 몇 가지의 색을 손쉽게 사용
생성자: RGB를 사용하여 원하는 색을 만들어서 사용
-Foreground color(전경색, 글자색)와 Background color(배경색, 바닥색)

사용법)
-색을 설정하는 method는 JComponent에 제공

글자색 설정)

-Constant
컴포넌트객체명.setForeground(Color.상수명)

-생성
컴포넌트객체명.setForeground(new Color(R,G,B));
컴포넌트객체명.setForeground(new Color(RGB를 16진수));

Background color(바닥색)
-불투명도가 사용된 Component는 투명하게 컴포넌트가 올라간 바닥컴포넌트의 색이 보인다.
-불투명도(opaque)를 활성화해야한다. setOpaque(true);

글자색 설정)

-Constant
컴포넌트객체명.setBackground(Color.상수명)

-생성
컴포넌트객체명.setBackground(new Color(R, G, B));
컴포넌트객체명.setBackground(new Color(RGB를 16진수));

