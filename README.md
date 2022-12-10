# interview
### 기술면접 예상 질문을 달아보는 공간입니다.
---

## 객체 지향

### 1. 프레임워크와 라이브러리 차이는 무엇인가요?
```
  프레임워크와 라이브러리의 가장 큰 차이점은 어플리케이션 흐름을 제어하는 주체가 누구인가입니다.
  라이브러리는 개발자가 개발을 할 때 사용하는 비휘발적인 함수들의 집합으로 일종의 도구를 말합니다. 
  라이브러리만 사용하면 개발자가 직접 어플리케이션의 흐름을 제어해야하지만, 
  프레임워크를 사용하면 제어의 역전을 통해 프레임워크가 어플리케이션을 동작합니다.
  따라서, 프레임워크룰 사용하면 개발자는 기능 구현에 집중하고, 개발시 공통적으로 필요하는 부분, 예를 들어 DB연동은 프레임워크에 맡길 수 있습니다.
  -  프레임워크에는 자바에 spring, 파이톤의 Django, Flask 등이 있습니다.
  -  라이브러리에는 JQuery, React.js 등이 있습니다.
  rf. https://cocoon1787.tistory.com/745
```
<br>

### 2. 추상클래스와 인터페이스의 차이에 대하여 설명해주세요
```
  추상클래스는 클래스내 abstract method가 하나 이상 존재하는 클래스를 말하며, super class의 기능을 상속하기 위해 사용합니다. 
  인터페이스는 모든 method가 public abstarct로 이루어져 있으며, 다중상속이 가능하고, 다양한 객체들에 동일한 동작을 부여하기 위해 사용됩니다.
  rf. JDK8 이후에는 인터페이스에 default와 static 사용이 가능해졌다.
  rf. https://brunch.co.kr/@kd4/6
```
<br>

### 4. SOLID 원칙에 대해서 설명해주세요.
SOLID 원칙이란, 로버트 C 마틴에 의해 만들어진 객체 지향 프로그래밍 및 설계의 다섯가지 원칙을 말합니다.
S(SRP) : 단일 책임 원칙은 한 클래스는 하나의 책임만 가져야 한다는 것을 말하며,
O(OCP) : 개방 폐쇄 원칙은 확장에는 열려 있고, 변경에는 닫혀 있는 것으로 반복적인 if절 보다는 하나의 인터페이스를 통해 확장성 있게 기능을 사용할 수 있도록 하는 원칙을 말합니다.
L(LSP) : 리브코프 원칙은 하위 타입은 언제나 기반이 되는 상위 타입으로 교체할 수 있어야 한다, 곧, 하위 클래스는 상위 클래스의 기능을 구현해야 한다는 것을 말하며,
I(ISP) : 인터페이스 분리 원칙은 인터페이스 또한 단일 책임을 가져야 한다는 것을 말하고,
D(DIP) : 의존성 역전 원칙은 하위 모듈의 변경이 상위 모듈의 변경을 요구하는 의존성을 끊어내는 것으로, 이는 프레임워크를 사용해 주어진 틀 안에서 라이브러리만 교체하는 것과 같은 원리를 말합니다.

<br>

## 자료구조

### 5. 트리 구조에 대하여 설명해주세요
트리는 계층 모델이자, ACyclic한 단방향 그래프를 말합니다. 
최상위 노드부터 시작하여, 인접한 좌우의 노드가 존재합니다.
종류로는 이진 트리, 균형 트리, 힙 트리 등이 존재합니다.
폴더 구조나, 조직도, 가계도, 또는 데이테베이스의 인덱싱을 할 때에 사용합니다.

<br>

## 알고리즘

### 1. 동적프로그래밍이란 무엇인가요?
```
  동적 프로그래밍(Dynamic Programming) 다른 말로 동적 계획법이란, 큰 문제를 여러개의 작은 문제로 나누어 푸는 방법을 말합니다. 
  작은 문제들이 반복되어 나타나야하며, 작은 문제들의 결과값이 항상 같을 때 사용할 수 있습니다.
  모든 작은 문제들은 한 번만 게산해 DP테이블에 저장하며, 추후 사용할 때는 이 DP테이블을 사용합니다. (이 방식을 메모이제이션이라고 합니다.)
  동적 프로그래밍은 타뷸레이션(bottom-up, for문), 메모이제이션(top-down, 재귀)을 통해서 구현할 수 있습니다.
```

<br>

## 데이터베이스

### 6. rdbms 와 nosql 차이에 대해 설명해주세요.
RDBMS는 관계형 데이터 베이스 시스템으로, 2차원의 구조화된 테이블 안에 데이터를 저장하고 관리하며, 각 vendor에 맞는 SQL 언어를 사용합니다.
NoSQL은 Not only SQL의 약자를 말하며, SQL만 사용하지 않는 저장소를 말합니다. key-value나 key-document, graph 등 다양한 형태로 저장이 가능합니다.
- RDBMS의 경우 정해진 스키마가 있기 때문에 데이터 구조가 명확하며, 각 데이터를 중복없이 저장할 수 있으나, 테이블이 많아질 수록 JOIN문이 많아지는 쿼리가 발생할 수 있고, 성능 향상을 위해서는 scale-up이 불가피하며, 스키마로 인해 데이터가 유연하지 않다는 단점을 가지고 있습니다.
- NoSQL의 경우 스키마 규격이 정해져 있지 않아 자유로운 데이터 구조를 가질 수 있으며, scale-up 뿐 아니라, scale-out 또한 가능합니다. 저장된 데이터를 언제든 조정하고 새로운 필드를 추가할 수 있다는 장점을 가지고 있습니다.
하지만 데이터 중복이 발생할 수 있고, 명확한 구조가 정해져 있지 않기 때문에 데이터 구조를 결정하기 어려울 수 있습니다.
- RDBMS는 데이터 구조가 명백하여 변경될 여지가 없는 경우에 사용하는 것이 좋고, NoSQL의 경우 정확한 데이터 구조를 알 수 없고, 변경 및 확장될 가능성이 높은 경우에 사용하는 것이 좋습니다.
rf. scale-out은 하나의 장비에서 처리하는 걸 여러 장비로 나누는 것(=서버 노드 대수를 나눈다), scale-up은 하드웨어 장비의 성능을 높이는 것(CPU를 변경하거나, 더 빠른 RAM 추가 등)
rf. <a href= "https://khj93.tistory.com/entry/Database-RDBMS%EC%99%80-NOSQL-%EC%B0%A8%EC%9D%B4%EC%A0%90">RDB와 NOSQL차이점</a>

<br>

## 운영체제

### 1. 프로세스의 구조에 대해 설명해주세요.
프로세스는 일반적으로 코드, 데이터, 힙, 스택으로 구성되어 있습니다. 코드는 말그대로 프로그램 코드를 저장하며, 데이터는 일반적으로 전역변수를 저장하고, 힙은 동적으로 할당되는 메모리 공간을 말하며, 스택은 함수를 호출할 때 쌓이는 메모리 공간을 말합니다. (지역변수 저장)

<br>

### 2. 프로그램과 프로세스의 차이점에 대해 설명해보세요.
프로그램은 실행되기를 기다리는 코드의 묶음을 말하며, 프로세스는 이러한 코드가 CPU에 적재되어 실행될 수 있는 상태를 말합니다.

<br>

### 3. 쓰레드가 무엇인지 설명하세요.
쓰레드란 프로세스 안에서 실제로 작업을 수행하는 주체를 말합니다. 
일종의 일꾼으로 표현을 많이 하며, 하나의 프로세스 안에서 여러 일꾼이 존재할 때 이를 멀티 쓰레드 프로세스라고 합니다.

<br>

### 4. 프로세스와 쓰레드의 차이점을 말해보세요.
프로세스는 운영체제로부터 자원을 할당받으며, 프로세스 간에 독립적인 주소 공간을 가지고 있습니다.
반면, 쓰레드는 프로세스로부터 자원을 할당받으며, 하나의 프로세스 주소 공간 안에서 스택만 분리하여 사용하므로, 데이터/코드/힙 영역을 공유합니다.

<br>

### 5. 컨텍스트 스위칭에 대해 말해보세요.
CPU는 한 번에 하나의 작업만 가능하기 때문에 여러 프로세를 돌아가면서 처리를 하는데 이 때 사용하는 것이 컨텍스트 스위칭입니다.
컨텍스트 스위칭은 프로세스 전환이 필요할 때, 기존 프로세스의 상태 정보를 PCB에 저장하고, 다음 프로세스의 상태 정보를 CPU에 업데이트 한 뒤 실행합니다.
<br> 
* 컨텍스트란 프로세스를 실행하기 위한 정보를 말한다.

<br>

### 6. 프로세스 간의 통신과 쓰레드 간의 통신에 대해 비교해서 설명하세요. (통신 기술의 필요 유무)
프로세스 간에는 서로 주소 공간이 분리되어 있어, IPC(Inter-Process Communication)를 통해 소통을 합니다.
반면, 쓰레드 간에는 서로 하나의 프로세스 주소 공간 안에서 코드/데이터/힙 공간을 공유하기 때문에 별도의 통신 기술이 필요하지 않습니다.

<br>

### 7. 멀티 쓰레드와 멀티 프로세스의 차이점에 대해 말하고, 둘을 언제 써야 하는지 말해보세요.
멀티 프로세스는 두 개 이상의 프로세서가 하나 이상의 작업을 병렬적으로 동시에 처리하는 것을 말하며,
멀티 쓰레드는 하나의 프로세스 안에서 여러 개의 일꾼이 동시에 작업을 처리하는 것을 말합니다.
멀티 프로세스의 경우 각 프로세스가 독립적인 주소 공간을 가지기 때문에 하나에 문제가 발생해도 다른 쪽까지 영향을 미치지 않습니다.
하지만, 그만큼 메모리 공간 할당량이 높고 컨텍스트 스위칭이 잦아 성능이 떨어질 수 있다는 단점을 가지고 있습니다.
멀티 쓰레드의 경우, 하나의 프로세스 안에서 여러 개의 스택이 동시 다발적으로 처리가 이루어지기 때문에,
하나의 쓰레드에 문제가 발생하면 다른 쓰레드까지 영향을 미칠 수 있으며, 동기화에 대한 이슈가 발생할 수 있습니다.
따라서, 만약 조회만 하는 경우 멀티 쓰레드를 사용하는 것이 적합하며, 읽고 쓰기가 빈번한 경우 멀티 프로세스를 사용하는 것이 적합할 수 있습니다.

(1) 멀티 프로세스
- 멀티 프로세스는 두 개 이상의 프로세서(CPU)가 협력적으로 하나 이상의 작업을 동시에 처리하는 것을 말합니다.(병렬처리)
- 각 프로세스 간에 메모리 구분이 필요하거나 독립된 주소 공간을 가져야할 때에 사용합니다.
- 장점 : 독립되어 있어 하나에 문제가 발생해도 다른 하나에 영향을 주지 않아 전체가 정지 되지 않습니다.
- 단점 : 작업량이 많을 수록 컨텍스트 스위칭이 자주 일어나, 오버 헤드가 발생해 성능 저하가 발생할 수 있습니다.
(2) 멀티 쓰레드
- 멀티 쓰레느는 하나의 프로세스 안에서 여러 개의 일꾼이 동시에 작업을 처리하는 것을 말합니다.
- 장점 : 시스템 자원 소모 감소, 시스템 처리율 향상, 컨택스트 스위칭이 적음
- 단점 : 하나의 스레드에 문제가 발생하면 전체 프로세스가 영향을 받음. 자원을 공유하기 때문에 동기화 이슈 (병목현상(=한 쪽으로 쏠림), 데드락 등) 가 발생할 수 있습니다.

### 6. 쓰레드 동기화에 대해 설명하시오.

### 7. 뮤텍스와 세마포어란 무엇입니까?

### 8. 데드락에 대해 설명하세요.

### 9. 가상 메모리와 페이징 시스템에 대해 설명하세요.

### 10. 요구 페이징과 페이지 폴트에 대해 설명하세요.
