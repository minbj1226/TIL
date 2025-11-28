# useBean 액션태그로 web parameter 받기
- request.getParameter()나 request.getParameterValues()를 사용하지 않고 web parameter를 받을 수 있다.

<b>주의
- HTML Form Control의 name 속성의 값과 같은 이름으로 DTO에 setter method가 제작된 경우에만 받아진다.
ex)

```
public class DTO {
	private int 이름;
	
	public void set이름(int 이름){
	}
	
	public 데이터형 get이름(){
	}
}
```
