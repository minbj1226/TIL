# web parameter 전송
- querystring 방식, JSONObject 방식 두 가지를 사용할 수 있다.
- 개발자가 parameter명과 값을 만들어서 전송하기 때문에 `<form>` 태그가 필요없다.

## QueryString 방식

```
var param="이름="+변수명+"&이름="+변수명 ,,,

$.ajax({
	url:"a.jsp",
	type:"get",
	data:param
})
```

## JSONObject 방식

```
var param={이름: 값, 이름: 값,,,};

$.ajax({
	url:"a.jsp",
	type:"get",
	data:param
})
```

## JSONObject parsing
- 데이터에서 원하는 부분을 잘라내서 사용하는 것 

문법)
``JSONObject객체명.이름;``

사용법)

- jsonObj
``var jsonObj={name: "민병조", age: 20};``

- parsing
``var name=jsonObj.name;``

## JSONArray parsing
- 반복문을 사용하면 모든 값을 parsing

문법)

```
$.each(JSONArray객체, function(인덱스, 방의값) {
	JSONObject객체명.이름;
});
```

## 복합형태의 JSONObject parsing

```
var jsonObj={
	dataLeng: 3, resultFlag: true
	data:[{name:"민병조", age:20}, {name="민병조", age:20}, {name="민병조", age:20}]
}
```
- 부가적인 정보 (JSONObject parsing)
변수명.이름
jsonObj.dataLeng

- 데이터 얻기 (JSONArray parsing)
var 변수명=변수명.이름;
var jsonArr=jsonObj.data

```
$.each(jsonArr, function(인덱스, 방의값을 저장할 변수) {
	방의값을 저장할 변수.이름
});
```

* AJAX에서 응답이 200으로 떨어지면 요청은 성공적으로 서버에 넘어갔지만 출력 형태가 잘못돼서 발생한 문제이므로 dataType을 변환해서 테스트