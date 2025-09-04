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
