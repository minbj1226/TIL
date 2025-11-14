# Java EE(Enterprise Edition) > 추후(Jakarta EE 변경)
- 기업에서 사용하는 프로그램을 개발하는 용도로 만들어진 Java의 개발 버전
- EJB(Enterprise Java Beans), Servlet/JSP, java mail 등을 개발할 수 있는 버전

## EJB
- 업무를 모듈로 구분하여 개발하고(약결합) 서비스 하기위해 개발된 기능
- 단점: 무겁다, 서비스하기 위한 별도의 (J2EE Server)가 필요
- 장점: 안정성이 높다, 약결합, 분산시스템을 지원

## Servlet/JSP
- 웹 개발용(동적으로 HTML을 생성)
- Java EE Spec 중 웹 서비스를 구현하기 위해 CGI를 준수하여 제작된 클래스들
- 동적으로 HTML을 생성하기 위해서 사용(개인화)
- CGI(Common Gateway Interface)
	- 일반언어로 웹 서비스하기 위해서 공통방식을 정의한 것
	- C언어가 CGI를 준수하면 C-CGI
	- Java언어가 CGI를 준수하면 Servlet
	- 장: 언어에서 제공하는 모든 기능을 사용할 수 있다.
	- 단: 속도가 느리다.(개발 속도도 느리고, 서비스 속도도 느림)

- 서비스 하기 복잡하다(DD: Deployemnt Descriptor)
	- web browser는 HTML만 실행할 수 있다. 
	- 서블렛(.class)을 실행할 수 없다 => DD가 필요