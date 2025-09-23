## Variable(변수)
-목적: 프로그램에서 필요한 값을 일시적으로 저장하고 사용할 때.
-값에 대해 별명을 부여하여 가독성을 향상시키기 위해서
-모든 데이터형을 사용하여 변수를 만들고 사용
-java에서는 instance variable(member variable), static variable, local variable 3가지 형태의 변수를 제공

*사용법)
1.변수의 선언
2.값 할당
3.값 사용(출력, 연산, 재할당 셋 중 하나는 반드시 해야 한다.)

1.선언)
데이터형 변수명; //지역변수는 자동초기화가 되지 않는다. 초기화 값을 설정해야 한다.<br>
``int myAge;``

2.값 할당)
변수명=값;<br>
``myAge=25;``

3.값 사용)
System.out.println(변수명);<br>
``System.out.println(myAge);``

*Data Type(데이터 형)
-값을 저장하기 위해 저장할 값의 종류에 따라 미리 메모리에 이름을 부여해 놓은 것
-변수를 선언할 때
-기본형 데이터형과 참조형 데이터형 두 가지를 제공

### Local Variable(지역 변수)
-method안에서 ( 영역{} )선언되고, method 안에서 사용하는 변수
-method외부에서는 지역 변수를 사용할 수 없다.
-자동초기화가 되지 않기 때문에 개발자가 반드시 초기화하여 사용
-초기화하지 않은 변수를 사용하면 error가 발생한다.
-method를 호출하면 memory에 올라가고, 호출이 끝나면 memory에서 내려온다.

```
class 클래스명{								 ---
	int i; //instance(member) variable				   |
	static int j; //static(class) variable			   |
									   class |
	public static void main(String[] args){	---		   |
		int k; //local variable		  local |  		   |
	}							---   	 ---
}
```

