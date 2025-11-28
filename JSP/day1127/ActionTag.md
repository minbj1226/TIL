# Action Tag(표준액션)
- 태그 자체가 정해진 일을 수행하는 태그

## Action Tag 사용법
``<jsp:태그명 속성="값" 속성="값" ,,,></jsp:태그명>``
``<jsp:useBean>``, ``<jsp:setProperty>``, ``<jsp:getProperty>``, ``<jsp:setProperty>``, ``<jsp:include>``, ``<jsp:forward>``, ``<jsp:param>``


## jsp:usebean 액션태그
- DTO(Data Transfer Object)나 VO(Value Object)를 객체화하여 scope 객체에 설정할 때
- 객체화 + scope 객체의 설정을 묶어놓은 태그
- `<jsp:useBean>` 으로 객체를 만들고, `<jsp:setProperty>`으로 setter method 호출하고, `<jsp:getProperty>`으로 getter method를 호출한다.

### jsp:usebean 사용법
1. 객체화) - default constructor를 사용하여 객체화
``<jsp:useBean id="객체명" class="패키지명.클래스명" scope="객체화 후 객체의 사용범위"/>``

2. 값할당) - setter method 사용
``<jsp:setProperty name="객체명" property="set을 제외한 method명 소문자" value="값"/>``

3. 값사용) - getter method 사용, web browser로 출력까지 함께 수행
``<jsp:getProperty name="객체명" property="get을 제외한 method명 소문자"/>``