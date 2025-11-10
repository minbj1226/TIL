# JSON(JavaScript Object Notation)
- 값을 가진 객체
- 문자열, 숫자, 불린, 함수를 저장하고 사용할 수 있다.
	- 함수: 일반 언어가 method나 function을 First Class Function으로 지원하지 않으면 사용할 수 없다.

- 이름과 값의 쌍
- 저장된 데이터는 이름을 사용하여 값을 얻을 수 있다.(parsing)
- JSONObject, JSONArray를 사용할 수 있다.

## JSON 형식
형식)
```
{이름: 값,,,}
``` 

- 값
	- 문자열(String): "값", '값'
	- 숫자(number): 정수(11), 실수(11.01)
	- 불린(boolean): true, false 
	- 함수(function): 무기명 함수
	
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
```
var 변수명=jsonObj.이름;
변수명();
```

4. JSONObject 값 추가(동일 이름이 JSONObject에 존재하면 덮어 쓴다)
``jsonObj.이름=값;``

5. 값 삭제
``delete jsonObj.삭제할 이름;``

## JSONArray
- JSONObject의 배열

문법)
``[ {이름:값,,,}, {이름:값,,,}, {이름:값,,,},,, ]``

사용법)
```
1. JSONArray 생성
var jsonArr=[{name:"민병조", age:25}, {name:"이지원", age:26},,,];

2. 반복

var jsonObj; //반복되는 JSONObject을 저장할 변수

for(var i=0; i<jsonArr.length; i++){
	jsonObj=jsonArr[i];
	
3. JSONObject에서 Data를 Parsing(jsonObj.이름)
	jsonObj.name
	jsonObj.age
	
	값이 없음의 비교 undefined 또는 "undefined"로 비교
	if(변수명==undefined) {
		//없음때의 처리
	}
}//end for	
```