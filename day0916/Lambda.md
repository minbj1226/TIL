## Lambda식
- JDK1.8(Java Se 8)에서부터 추가된 기능
- 인터페이스를 편하게 사용하기 위해서 추가된 기능
인터페이스 사용
-클래스 파일을 생성
1.인터페이스를 구현한 클래스를 하나 만들어서
2.abstract method Override
3.인터페이스를 구현한 클래스를 개체화하여 사용

-클래스 파일을 생성x
1.annonymous inner class 문법으로 생성
2.abstract method Override

-functional Interface(abstract method를 하나만 가지고 있는 interface, 인터페이스 위에는 필요하다면 @FunctionalInterface annotation을 설정 가능)만 적용가능하다.

문법)
``(매개변수,,) -> { 구현코드 }``

예)
1.인터페이스 선언

```java
@FunctionalInterface
public interface Test{
	public void temp(int i);
}
```

2.Lambda식으로 호출
인터페이스명 객체명=(매개변수,,,)->{구현코드,,,};

``Test t=(int i) -> {System.out.println(i);};``

3.호출
t.temp(20);

method형)
-고정일) 반환형 없고, 매개변수 없는 형
``public void test();``

구현)
인터페이스명 객체명=() -> {코드 구현,,,return int};

호출)
데이터형 변수명=객체명.method명();

-가변일) 반환형 없고, 매개변수 있는 형
``public void test(String name, int age);``

구현)
인터페이스명 객체명=(String n, int a) -> { 코드 };

호출)
객체명.method명("값", 정수값);