# Event Handlling
- 사용자의 동작이 있을 때, 그 동작에 대한 대비코드를 만들고 실행하는 것

문법)
- on 함수

```
$("selector").on("이벤트종류", 무기명함수(){
	이벤트가 발생했을 때 처리할 코드
});

document.getElementById("아이디").addEventListener("click", First Class Function)
```

- 이벤트 함수

```
$("selector").이벤트함수(무기명함수() {
	이벤트가 발생했을 때 처리할 코드
});
``` 