# DTD(Document Type Definition)읽기
- ML에서 사용하는 태그(노드)들을 정의한 파일
- DTD에서 정의한 노드만 사용할 수 있다.

기호|의미
,| 순서대로 작성
?| 0~1: 노드를 작성하지 않을 수 있지만, 작성한다면 한개만 만들 수 있다.
*| 0~n개: 노드를 작성하지 않을 수 있고, 작성한다면 여러개 작성할 수 있다.
+| 1~n개: 노드를 반드시 작성해야할 때

# log
- 프로그램의 실행정보를 파일로 저장하거나,  출력할 목적으로 사용하는 프로그램
- SLF4J, Apache Commons Logging, Log4j 2, Log4j(deprecated since 3.5.9), JDK logging의 다양한 logger를 지원한다
- log는 동작하는 로그레벨이 제공된다(설정하는 로그 레벨에 따라 로그파일에 출력되는 정보가 달라진다)
- System.out.println(디버그코드); => 반드시 찾아서 삭제해야한다.(관리가 어렵다) => log level을 사용하면 소스코드를 사용하지 않고 필요에 따라 출력된다.

## log 사용법
1. 관련 jar 다운 설치
2. MyBatis Framework을 사용하는 code에서 log method를 추가
3. Log가 동작하는 설정파일 작성
4. Class path 최상위에 작성된 파일을 생성 배포

## Mapper 작성법
- Query문이 정의되는 XML
1. 설정파일(mybatis-config.xml)에서 mapper node로 Mapper.xml을 연결한다
2. Mapper.xml에 쿼리문을 작성
	- insert
	
# Lombok 
- DTO의 기본 생성자, 매개변수 있는 생성자, getter, setter method를 annotation으로 자동 생성하는 Framework
- 설치하여 사용하는 Framework

설치법)
``java -jar 배포된 jar명``

사용법)
외부값 없이 insert

```
<insert id="아이디">
	insert into 테이블명(컬럼명,,,) values();
```
외부값으로 insert