
# 자바 핵심 개념 정리 3
<details>
<summary>POJO란 무엇일까요?</summary>
<div markdown="1">
<b>Plain Old Java Object</b><br> : Java로 생성하는 순수한 객체<br>
- POJO는 객체 지향적인 원리에 충실하면서 환경과 기술에 종속되지 않고, 필요에 따라 재활용될  수 있는 방식으로 설계된 오브젝트를 의미 <br>
<br>
<b>POJO 프로그래밍</b><br>
- POJO 프로그래밍은 POJO를 이용하여 프로그래밍 코드를 작성하는 것<br>
- 준수해야하는 규칙<br>
    1. Java나 Java의 스펙에 정의된 것 이외에는 다른 기술이나 규약에 얽매이지 않아야 한다.<br>
    2. 특정 환경에 종속적이지 않아야 한다<br>
<br>
<b>POJO 프로그래밍이 필요한 이유</b><br>
- 특정 환경이나 기술에 종속적이지 않으면 재사용 가능하고, 확장 가능한 유연한 코드 작성 가능, 또한 테스트 단순해짐<br>
- 저수준 레벨의 기술,환경 종속적 코드를 제거해 간결한 코드 작성이 가능하고 디버깅이 보다 쉬워짐<br>
- (중요) 객체지향적인 설계를 제한 없이 적용할 수 있다! <br>
<br>
<b>POJO와 Spring의 관계</b><br>
- Spring은 POJO 프로그래밍을 지향하는 프레임워크<br>
-스프링에서의 POJO 삼각형 : IoC/DI, AOP, PSA를 통해서 달성할 수 있다는 것을 의미<br>
- Spring 프레임워크는 IoC/DI, AOP, PSA 지원하고 있음<br>
<br>
참고 블로그 : https://ittrue.tistory.com/211
</div>
</details>
<br>

<details>
<summary>제너릭이 무엇인가요? 컬렉션 클래스에서 제너릭을 사용하는 이유를 설명해 주세요.</summary>
<div markdown="1">
<b>제너릭</b> <br>
: 데이터 타입을 일반화하는 것으로 데이터 타입을 컴파일시 미리 지정해 두는 것을 말함<br>
<b>사용 이유</b><br>
 - 컴파일 시에 미리 타입이 정해지므로, 타입의 안정성을 높이고 형 변환의 번거로움을 줄일 수 있음 <br>
 - 타입만 변경해서 수정하기 용이함
</div>
</details>
<br>

<details>
<summary>자바의 클래스 멤버 변수 초기화 순서에 대해 알려주세요.</summary>
<div markdown="1">
<b>클래스 변수의 초기화 시점</b><br>
- 클래스가 처음  로딩될 때 단 한번 초기화 됨<br>
<br>
<b>자바 클래스 멤버 변수들의 초기화 순서</b><br>
1. static 변수 선언부<br>
: 클래스가 로드될 때 변수가 가장 먼저 초기화됨<br>
2. 필드 변수 선언부<br>
:객체가 생성될 때<br>
3. 생성자 block<br>
:객체가 생성될 때 필드 변수 선언 이후
<br>
<br>
참고 블로그 : https://eyevsky.tistory.com/entry/Java-%ED%81%B4%EB%9E%98%EC%8A%A4-%EB%A9%A4%EB%B2%84-%EB%B3%80%EC%88%98%EB%93%A4%EC%9D%98-%EC%B4%88%EA%B8%B0%ED%99%94-%EC%88%9C%EC%84%9C
</div>
</details>
<br>

<details>
<summary>직렬화란 무엇인가요?</summary>
<div markdown="1">
<b>직렬화란?</b><br>
(=serialization)<br>
: 데이터 스토리지 문맥에서 데이터 구조나 오브젝트 상태를 동일하거나 다른 컴퓨터 환경에 저장하고 나중에 재구성할 수 있는 포맷으로 변환하는 과정 [위키백과]<br>
<br>
<b>객체의 직렬화란?</b><br>
: 객체의 내용을 바이트 단위로 변환하여 파일 또는 네트워크를 통해서 스트림(송수신)이 가능하도록 하는 것을 의미<br>
- 자바의 I/O 처리는 정수, 문자열 바이트 단위의 처리만 지원했기에 복잡한 내용 전달 위해선 패킷형식으로 전송 했어야함.<br>
- 객체의 직렬화로 자바 I/O가 자동적으로 객체의 내용을 바이트 단위로 변환해 저장,전송할 수 있도록 해줌<br>
- 객체의 멤버 변수가 다른 객체의 레퍼런스 변수인 경우 그 객체까지 직렬화하여 트리구조로 연속적으로 일어나게됨<br>
<br>
<b>장점</b><br>
- 객체 내용을 입출력 형식에 구애받지 않고 객체를 팡리에 저장함으로써 영속성 제공<br>
- 손쉽게 객체 교환 가능<br>
<br>
<b>객체 전송 단계</b><br>
- 바이트 단위로 분해-> 순서에 따라 전송 -> 전송 받은 데이터 원래대로 복구
<br>
<br>
참고 블로그: https://weicomes.tistory.com/63
</div>
</details>
<br>

<details>
<summary>[예습] SOLID에 대해 알아봅시다.</summary>
<div markdown="1">
<b>SOLID란 OOP의 5가지 원칙을 말함</b><br><br>
<b>SRP : 단일 책임의 원칙</b><br>
    - 한 클래스는 하나의 책임만 가져야 한다.<br>
    - ‘하나의 책임’? 기준이 모호 → 중요한 것은 변경!<br>
    - 변경이 있을 때 파급 효과가 적으면 단일 책임 원칙을 잘 따른 것이라 할 수 있음<br>
    <br>
<b>OCP : 개방-폐쇄 원칙</b><br>
    - 소프트웨어의 요소는 확장에는 열려있으나, 변경에는 닫혀있어야 함
    - 즉, 다형성을 활용하여 원칙을 따를 수 있음<br>
    - ex) 인터페이스를 구현한 새로운 클래스를 하나 만들어서 새로운 기능을 구현<br>
    <br>
<b>LSP : 리스코프 치환 원칙</b><br>
    - 프로그램의 객체는 프로그램의 정확성을 깨뜨리지 않으면서 하위 타입의 인스턴스로 바꿀 수 있어야 함<br>
    - 다형성에서 하위 클래스는 인터페이스 규약을 다 지켜야한다는 것, 다형성을 지원하기 위한 원칙.<br>
    <br>
<b>ISP : 인터페이스 분리 원칙</b><br>
    - 특정 클라이언트를 위한 인터페이스 여러 개가 범용 인터페이스 하나보다 낫다<br>
    - 인터페이스가 명확해지고, 대체 가능성이 높아짐<br>
    <br>
<b>DIP  : 의존관계 역전 원칙</b><br>
    - 구현 클래스에 의존하지 않고 인터페이스에 의존하라는 것<br>
    - 이래야 변경에 용이함<br>

---

- 다형성 만으로는 OCP, DIP를 지킬 수 없다 → 스프링으로 해결
</div>
</details>
<br>

<details>
<summary>[예습] DI는 무엇일까요?</summary>
<div markdown="1">
DI: 의존성 주입<br>
- 객체가 의존하는 또 다른 객체를 외부에서 선언하고 이를 주입받아 사용하는 것 (느슨한 결합 관계)<br><br>
스프링에서의 DI<br>
- 각 클래스 사이에 필요로 하는 의존 관계를 빈 설정 정보를 바탕으로 컨테이너가 자동으로 연결해주는 것<br>
</div>
</details>
<br>