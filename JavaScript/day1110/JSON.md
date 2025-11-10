# JSON(JavaScript Object Notation)
- 값을 가진 객체
- 문자열, 숫자, 불린, 함수를 저장하고 사용할 수 있다.
	- 함수: 일반 언어가 method나 function을 First Class Function으로 지원하지 않으면 사용할 수 없다.

- 이름과 값의 쌍
- 저장된 데이터는 이름을 사용하여 값을 얻을 수 있다.(parsing)
- JSONObject, JSONArray를 사용할 수 있다.

## JSON 형식
형식)
```JSON
{이름: 값,,,}
``` 

- 값
	- 문자열(String): "값", '값'
	- 숫자(number): 정수(11), 실수(11.01)
	- 불린(boolean): true, false 
	- 함수(function): a무기명 함수
	
### JSON 형식의 문자열, 객체생성
사용 예)
- 문자열 형식
1. 선언
``var txt="{이름:값,,,}";``

2. eval 함수를 사용하여 객체로 생성
``var jsonObj=eval("("+ txt +")")``

- JSONObject 형식(권장)
``var jsonObj={이름:값,,,};``

3. JSONObject Parsing(값을 잘라내서 사용)
- 값 얻기(문자열, 불린, 숫자)
``var 변수명=jsonObj.이름;``

- 값 얻기(함수)
```JSON
var 변수명=jsonObj.이름;
변수명();
```

4. JSONObject 값 추가(동일 이름이 JSONObject에 존재하면 덮어 쓴다)
``jsonObj.이름=값;``

5. 값 삭제
``delete jsonObj.삭제할 이름;``