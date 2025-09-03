MVC pattern이 도입된 Component들
==============================
-JList, JTable, JComboBox 존재
-데이터의 처리, 화면 처리, 이벤트 처리 업무를 구분하여 제공하는 Component들.
데이터의 처리: DefaultComboBoxModel
화면 처리: JComboBox
이벤트 처리 업무: ActionListener, ItemListener
-Model: 데이터를 가지고 관리하는 일(클래스명 DefaultXxxModel)
-Viewer: 데이터를 가진 모델을 사용하여, 사용자에게 보여주는 일
-Controller: 이벤트 처리와 관련된 일

-장점: 파일내의 코드 복잡도가 낮아진다, 유지보수가 편해짐
-단점: 파일의 개수가 많아진다, 값 넘기기가 불편하다, 에러처리가 불편

*JComboBox 사용
--------------------------------
1.Model 생성) - 데이터 관리
DefaultComboBoxModel<E> dcbm=new DefaultComboBoxModel<E>();

2.View 생성) - Model과 has a 관계로 View 생성.
JComboBox<E> jcb=new JComboBox(dcbm);

3.데이터를 추가) - Model 객체를 사용
dcbm.addElement("값");
dcbm.addElement(인덱스,"값");

4.Element의 값 얻기) View에서 발생하는 데이터를 활용하여, Model에서 값을 얻는다.
int ind=jcb.getSelectedIndex();
5.Element의 값 삭제) 
-View에서 선택한 엘리먼트의 번호얻기
-Model에서 해당 번호에 값을 삭제:

*JList 사용
---------------------------------
-DefaultListModel 클래스를 Model 객체로 사용하는 View 객체

사용법) 
1.Model 객체생성)
DefaultListModel<E> dlm=new DefaultListModel<E>();

2.View 객체생성)
Model 객체와 View 객체간의 관계는 has a
Jlist<E> jl=new Jlist<E>(dlm);

3.Model 객체 값 설정)
dlm.addElement(값);

4.값얻기
View객체에서 선택된 아이템의 번호를 얻고
int ind=jl.getSelectedIndex();

Model객체에서 선택된 값의 
dlm.getElementAt(ind);

5.값삭제
View객체에서 선택된 아이템의 번호를 얻고
int ind=jl.getSelectedIndex();

Model객체에서 선택한 아이템 번째 값을 삭제
dlm.removeElementAt(ind);

*JTable
-----------------------
-DefaultTableModel 클래스를 Model 객체로 사용하는 View 객체

사용법)
1.Model 객체 생성)
DefaultTableModel dtm=new DefaultTableModel(Object[][] <- 행과 열의 데이터, Object[] <- 열의 이름);

2.View 객체 생성)-Model과 has a 관계
Jtable jt=new JTabel(dtm);

3.Model 객체에 값 할당
일차원 배열 or Vector로 값을 넣는다.
dtm.addRow();