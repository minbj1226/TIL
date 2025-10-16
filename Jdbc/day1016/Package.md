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

- 특정 업무의 코드를 찾기 어려움

kr.co.sist.사용자.회원 - View, Evt, Service, DTO, DAO
kr.co.sist.사용자.주문 - View, Evt, Service, DTO, DAO
kr.co.sist.사용자.매출 - View, Evt, Service, DTO, DAO
