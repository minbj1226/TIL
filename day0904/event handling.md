# Event Handling

이벤트 처리란 디자인에서 사용자의 동작에 대한 대비 코드를 준비해두고 실행하는 것을 의미합니다. Java에서는 이벤트 관련 인터페이스와 클래스를 `java.awt.event`와 `javax.swing.event` 패키지에서 제공합니다.

## 이벤트의 종류

| 사용자 동작      | 발생하는 이벤트  | 이벤트 Listener       | 컴포넌트를 이벤트 등록 method                   | 사용 예                                                   |
|------------------|-----------------|-----------------------|-----------------------------------------------|----------------------------------------------------------|
| 클릭, 엔터       | `ActionEvent`   | `ActionListener`       | `addActionListener(리스너를 구현한 객체)`        | `JButton jbtn = new JButton("버튼");`<br> `jbtn.addActionListener(this)`<br> - `is a`<br> `jbtn.addActionListener(이벤트처리객체)` |
| 아이템 변경      | `ItemEvent`     | `ItemListener`         | `addItemListener(리스너를 구현한 객체)`          | `JComboBox jcb = new JComboBox();`<br> `jcb.addItemListener(this)`<br> `jcb.addItemListener(이벤트처리객체)` |
| 키보드의 키      | `KeyEvent`      | `KeyListener`          | `addKeyListener(리스너를 구현한 객체)`           | `JTextComponent`의 하위 클래스<br> `JTextField jtf = new JTextField();`<br> `jtf.addKeyListener(this)`<br> `jtf.addKeyListener(이벤트처리객체)` |
| 윈도우 메뉴 키가 눌렸을 때 | `WindowEvent`    | `WindowListener`        | `addWindowListener(리스너를 구현한 객체)`        | `JFrame` 또는 `JDialog` 객체에<br> `addWindowListener(this)`<br> `addWindowListener(이벤트처리객체)` |
| 마우스           | `MouseEvent`    | `MouseListener`        | `addMouseListener(리스너를 구현한 객체)`         | 마우스를 클릭할 수 있는 모든 컴포넌트들<br> `addMouseListener(this);` |

## 처리 순서

1. 컴포넌트를 이벤트에 등록한다.
2. 사용자가 동작을 수행한다.
3. JVM이 이벤트를 발생시킨다.
4. 이벤트 Listener가 이벤트를 받고, 정해진 코드를 수행한다.

## 작성법
1. 사용자의 동작에 의해 발생하는 이벤트를 처리할 수 있는 XxxListener 구현
```
public class Design extends JFrame implements ActionListener{
```
2. 생성자안에서 컴포넌틀를 생성/배치
```
public Desgin(){
	JButton jbtn=new JButton("클릭");
	2-1. 생성된 컴포넌트를 이벤트에 등록
	컴포넌트명.addXxxListener(이벤트가 발생했을 때 처리할 객체명);
}
```

3. XxxListener가 가진 abstract method를 Override
```
public void actionPerformed(ActionEvent ae){
	이벤트가 발생했을 때 사용자에게 제공하는 코드
}
```

##흐름
1. 사용자가 버튼을 클릭하면
2. JVM에 이벤트가 전달되면서 등록된 컴포넌트인지 판단
3. 이벤트에 등록된 버튼이라면 event 객체가 생성된다. Override method를 호출하면서 생성된 event 객체를 arguments로 할당한다.

##Window Event 처리
-java.awt.Frame은 x를 눌러서 종료할 수 없다. javax.swing.jFrame은 x를 클릭하면 객체는 살아있고, 눈에 보이지 않는 상태로 전환된다.
-java.awt.event.WindowListener 인터페이스를 구현하여, 7개의 abstract method를 모두 Override 한 후, windowClosing() 안에 Window 클래스에서 제공하는 종료 method인 dispose()를 호출한다.

##Keyboard Event 처리
-키보드의 입력이 가능한 JTextComponent의 하위클래스들은 키보드 이벤트를 처리할 수 있다.
-Keycode는 키에 대한 유일한 코드값: 대,소문자 코드값이 같다.
-ASCII code 문자의 값: 대,소문자의 코드값이 다르다.
-이벤트 처리 객체의 가장 윗 부모 EventObject에는 이벤트를 발생시킨 객체의 주소를 반환하는 getSource() 제공한다.
-같은 종류의 이벤트를 서로 다른 Component가 발생시키더라도 비교할 수 있다.

문법)
if(e.getSource()==컴포넌트 객체){

}