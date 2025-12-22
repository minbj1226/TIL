# MyBatis
- DB Mapper Framework(Persistence Framework, 영속성 Framework)
- Apache Software Foundation에서 iBATIS라는 이름으로 시작한 프레임워크(apache -> google -. github)
- 다양한 언어를 지원
- 언어에서 서용하는 데이터 형을 그래도 사용할 수 있다
- 유연성이 높다(쿼리문을 XML로 분리하여 작성하고 사용)
- 언어의 코드가 간결해진다.
- mybatis.org에서 다운 받을 수 있다.

## MyBatis 구조



## MyBatis 설정
1. WEB-INF/lib/mybatis-x.jar 배포, (MAVEN 사용)
2. 환경설정용 XML을 작성(mybatis-config.xml) => Driver, URL 계정, mapper 연결
3. Mapper 작성
4. MyBatis Frame 사용
	- SqlSessionFactoryBuilder: 설정파일과 연결된 Stream을 입력받아, DB연결관리 XML의 설정정보에 연결된 Mapper안의 쿼리문을 parsing > parsing된 쿼리문을 실행 > 결과를 만들어서 반환
	- SqlSessionFactory: SqlSessionFactoryBuilder의 부모
	- SqlSession: MyBatis Handler(MyBatis Framework을 사용하여 DB작업 수행)
5. 설정용 xml 연결
``Reader reader=Resources.getResourceAsReader("패키지명/설정파일명.xml");``
6. MyBatis Framework 생성
``SqlSessionFactory ssf=new SqlSessionFactoryBuilder().build(reader)``
7. MyBatis Framework을 사용할 수 있는 Handler를 얻기
``SqlSession ss=ssf.openSession();``
8. Handler를 사용
``ss.selectOne(), ss.selectList(), ss.insert(), ss.update(), ss.delete();``
9. Transaction 완료
``ss.commit(), ss.rollback();``
10. MyBatis Handler 닫기
``ss.close();``
