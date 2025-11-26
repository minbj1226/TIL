# Cookie
- 비연결성인 웹에서 관계를 유지하기 위해서 사용되는 클래스
- 내장객체가 아님(개발자가 직접 객체화하여 사용)
- 접속자의 HDD에 file이 생성되고, 생성된 파일의 문자열로만 정보가 저장된다.
- 최장 1년까지 유지
- 웹 브라우저에서 확인, 수정, 삭제도 가능
- 중요하지 않는 값 저장(아이디저장, 팝업창 오늘하루 창 닫기)

## Cookie 사용법
1. 객체화
``Cookie cookie=new Cookie("이름", "값");``

2. 생존시간 설정
``cookie.setMaxAge(초);``
*쿠키는 생존시간을 설정하지 않으면 브라우저가 종료될 때 같이 삭제된다.

3. 쿠키 심기(여러 개)
``response.addCookie(쿠키객체);``

4. 쿠키 읽기

```
Cookie[] cookies=request.getCookies()

cookies temp=null;
for(int i=0; i<cookies.length; i++) {
	temp=cookies[i];
	//쿠키 이름 얻기: temp.getName();
	//쿠키 값 얻기: temp.getValue();
}
```

5. 쿠키 삭제
- 삭제할 이름과 동일한 이름으로 쿠키를 생성
``Cookie cookie=new Cookie("이름","");``
- 생존시간 설정
``cookie.setMaxAge(0);``
- 쿠키 심기(여러개)
``response.addCookie(쿠키객체);``