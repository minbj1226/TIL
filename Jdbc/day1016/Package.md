# 패키지 구분
1. 기능 중심(Layered Architecture)
- MVC Pattern 구조를 사용할 때 나누면 좋음
- 계층별 역할이 명확
- 특정 업무의 코드를 찾기 어려움

kr.co.sist.사용자.view - (LoginForm, UserMain,,,)
kr.co.sist.사용자.controller - (LoginFormEvt, UserMainEvt,,,)
kr.co.sist.사용자.dao - (LoginDAO, UserMainDAO,,,)
kr.co.sist.사용자.dto -
kr.co.sist.사용자.service -

kr.co.sist.관리자.view
kr.co.sist.관리자

2. 도메인 중심(Domain-Driven Design)
- 도메인(기능-업무)단위로 코드가 그룹화
- 관련 기능을 찾고 수정하기 용이
- 모듈화가 구조적이어서 재 사용성이 높다.
- 업무로직(BL)을 도메인 중심으로 관리할 수 있다.
- 각 도메인마다 동일 클래스가 반복되어 중복 코드가 발생할 수 있다.
- 소규모 프로젝트에서는 패키지가 많지않아 

kr.co.sist.사용자.회원 - View, Evt, Service, DTO, DAO
kr.co.sist.사용자.주문 - View, Evt, Service, DTO, DAO
kr.co.sist.사용자.매출 - View, Evt, Service, DTO, DAO
