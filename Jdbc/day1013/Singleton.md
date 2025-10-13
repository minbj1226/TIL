# Singleton Pattern(GoF)
- 실행 중인 JVM에서 하나의 instance만 생성하고 사용하는 Design Pattern.
- 장점: 속도가 빠르다, 메모리 사용량이 적다.
- 단점: 사용중에 객체가 소멸되면 다시 살아나지 못한다. => 살아날 수 있도록 코드 작성<br>
값을 저장하는 변수가 선언되고, 사용하는 객체중에 하나가 값을 변경했을 때, 초기에 제공되어야 하는 값을 다른 객체에서 사용할 수 없다. => 값을 변경하지 못하도록 만들어야 한다.<br>

작성법)
1. 클래스 외부에서 직접 객체화하지 못하도록 만든다.
=> 생성자의 접근 지정자를 private으로 설정

```Java
public class Test{
	private static Test t;//선언-객체를 하나로 관리하기 위해서
	private Test(){//class 외부에서 객체화 불가
	}
}
```

2. 클래스의 instance를 생성하여 외부로 반환하는 일을 하는 method 작성

```Java
public static Test getInstance(){
	if(t==null) { //3. 객체를 하나로 생성할 수 있도록 조건설정, 조건: 객체가 존재하지 않으면 생성
		t=new Test();
	}
	return t; //생성된 객체가 반환되든, 새로 생성된 객체가 반환되든
}
```

## Properties 작성
- 이름과 값의 쌍을 가진 데이터형

- 형식
	이름=값 <= 띄어쓰기 매우 주의
	
- 주석: #

사용법)

1.생성)
``Properties prop=new Properties();``

2.method 호출)
- properties 파일을 로딩<br>
``prop.load(new FileInputStream(new File("파일경로")));``

3.properties 파일내 값 얻기<br>
``String 값=prop.getProperty("이름");``

ex) ``String url=prop.getProperty("url");``