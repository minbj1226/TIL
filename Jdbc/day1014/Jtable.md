# JTable
- 표 자체를 화면에 보여주는 UI컴포넌트
- 표를 그리는 역할만 하고, 데이터는 직접 가지고 있지 않는다.
- 표 안에 들어갈 데이터는 TableModel이 관리한다.

## DefaultTableModel
- JTable에 데이터를 공급하는 기본 데이터 모델 클래스

## 파일 추가(blob 데이터형 사용)
- FileInputStream을 사용하여 binary data로 추가
- PreparedStatement로만 가능

순서)
1.DBMS 테이블에 insert할 파일과 스트림을 연결<br>
```Java
File file=new File("insert할 파일의 경로");
FileInputStream fis=new FileInputStream(file);
```

2.PreparedStatement에 파일과 연결된 스트림을 넣어준다.<br>
``pstmt.setBinaryStatement(바인드변수 인덱스, 스트림, 파일크기);``

3.쿼리문 실행
