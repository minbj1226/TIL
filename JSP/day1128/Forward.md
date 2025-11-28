# jsp:forward 액션태그
- forward 방식으로 페이지를 이동할 때 사용(데이터 처리페이지와 화면 디자인 페이지를 분리하여 작성할 때)

# 사용법
- web parameter를 생성하지 않고 이동
``<jsp:forward page="이동할 페이지 URI"/>``

- web parameter를 생성하여 이동

```
<jsp:forward page="이동할 페이지 URI"/>
	<jsp:param name="이름" value="값"/>
	<jsp:param name="이름" value="값"/>
</jsp:forward>
```