*객체(instance)를 내보내거나, 읽기위한 목적의 스트림
-ObjectInputStream, ObjectOutputStream 제공
-기본형 데이터형은 Stream을 타고 나갈 수 있지만, 객체는 Stream을 타고 나갈 수 없다.(객체는 크기를 알 수 없기 때문에)
-8bit stream => 데이터를 한번에 한 byte씩 내보내는 스트림

-참조형 데이터형이 stream을 타고 나갈려면, 객체가 일정크기(8bit=> 1byte)로 쪼개져야하는데, 크기를 알 수 없기 때문에 몇개로 쪼개져야 할지 알 수 없다.
-객체는 중요한 값을 가질 수도 있기 때문에 JVM외부로 나가는 것을 막아놨다.(사용자 정의 자료형)
-JVM에서 기본형 데이터형이 외부로 나가는 것을 막을 때에는 transient 접근지정자를 사용한다.
-클래스 작성시 java.io.Serializable 인터페이스를 구현한 클래스의 객체는 직렬화가 되고 JVM 외부로 나갈 수 있다.