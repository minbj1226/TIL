# JUnit
- 자바 프로그래밍 언어용 Unit 테스트 프레임워크
- assert(단정) method로 테스트 케이스의 수행결과를 판별
- 테스트 결과를 시각적으로 보여준다.
- Annotation을 지원하여 간단한 테스트 수행

## 단위 테스트(Unit Test)
- 하나의 모듈을 기준으로 독립적으로 진행되는 가장 작은 단위의 테스트
- 모든 method에 대한 Test case 작성하여 의도된 대로 잘 동작하는지 검증
- System.out.println()으로 하는 번거로운 디버깅이 사용되지 않으므로 디버깅 시간을 줄일 수 있다.

### 단위 테스트 장단점
- 장점: 통합테스트는 시스템을 구성하는 모듈이 많아질수록 테스트 시간이 증가하는 반면, 단위 테스트는 해당 모듈을 독립적으로 테스트하기 때문에 테스트 시간이 줄어든다.<br> => 문제의 원인을 빠르게 찾아서 해결할 수 있다.
- 단점: 클래스의 수가 증가한다.

## 통합 테스트(Integration Test)
- 모듈을 통합하는 과정에서 모듈간의 호환성을 확인하기 위해 수행되는 테스트
- 애플리케이션은 여러 개의 모듈로 구성되고, 모듈끼리 값을 주고 받으면서 기능에 이상이 없는지 테스트 하는것.

## FIRST 규칙
- Fast: 테스트는 빠르게 동작하고 자주할 수 있어야함
- Independent: 각각의 테스트는 독립적이어야 함
- Repeatable: 반복 가능
- Self-Validation: 테스트는 성공, 실패를 boolean 값으로 자체 반환해야 한다.
- Timely: 테스트는 적시에 동작해야 한다. 

### assert method 제공
- assertArrayEquals(a, b): a와 b가 일치하는지 확인
- assertEquals(a, b): a와 b가 같은 값을 가지는지 확인
- assertNotEquals(a, b): a와 b가 다른 값을 가지는지 확인
- assertEquals(a, b, c): a와 b가 가진 값이 오차범위 내에 있는지 확인.(a-실행결과, b-예상겨로가, c-오차범위)
- assertSame(a, b): a와 b가 같은 객체인지 확인
- assertTrue(a): a가 true인지 확인
- assertNotNull(a): a가 null인지 확인
- assertThrows(예외처리 클래스.class, () -> 예외발생 예상코드): 해당 예외가 발생했는지 확인
- assertDoesNotThrows( ()-> 예외발생 예상코드): 예외가 발생하지 않았는지 확인

### annotation
- @Test: 테스트를 만드는 모듈
- @DisplayName: 테스트 클래스 또는 테스트 method에 사용자가 테스트명을 부여
- @BeforeAll: 테스트 대상 method가 실행되기전에 호출되어야하는 method (static 설정)
- @BeforeEach: 테스트 대상 method가 실행되기전에 호출되어야하는 method
- @AfterEach: 테스트 대상 method가 호출된 이후 호출되어야하는 method
- @Disable: 테스트 클래스 또는 테스트 method를 비활성화 할 때
 
## Junit 설정
1. Project > 오른쪽 버튼 클릭 > properties
2. Build path > Libraries > Add Library