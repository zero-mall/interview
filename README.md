# interview
### 기술면접 예상 질문을 달아보는 공간입니다.
---

## 백엔드 공통 질문

### 1. JWT란 무엇인가요? https://jwt.io/
JWT는 Json Web Token의 약자로, 웹 유저의 인증을 위해 사용하는 암호화된 토큰을 말합니다.
Header, Payload, Signiture 정보가 담겨 있습니다.
1) 유저 로그인 요청 --> 서버에서 회원 인증을 하고 JWT 토큰 발급 
2) 유저 요청 시 JWT 토큰을 헤더(ex. Authorization)에 넣어 전달 --> 서버에서 JWT 토큰 검증 후 응답     

### 2. OAuth란 무엇인가요?
OAuth란 인증(Authentication)과 권한(Authorization)을 획득하는 과정을 말합니다.
OAuth의 대표적인 예로는, 네이버, 카카오, 페이스북 로그인이 될 수 있습니다.
유저의 입장에서는 다양한 서비스에 회원가입을 하기 때문에 아이디나 비밀번호가 노출되는 것이 부담스러울 수 있습니다.
![image](https://user-images.githubusercontent.com/107039546/207290064-6d8415a9-b1a8-4913-b3a8-a3b4ea69f602.png)

### 3. 대칭키와 비대칭키란 무엇인가요?
(1) 대칭키란 암호화와 복호화에 사용되는 키가 동일한 키를 말합니다.
키값을 알고 있는 사람만이 문서를 복호화할 수 있으며, 공개키 방식에 비해 속도는 빠르지만, 키 교환 과정 중에 키가 탈취될 수 있고,
키 사용 유저가 증가할 수록 관리 포인트가 증가한다는 단점이 있습니다.
(2) 비대칭키, 또는 공개키란, 암호화와 복호화에 사용되는 키가 다른 것을 말합니다.
암호화 키(공개키)는 모든 사람이 접근 할 수 있지만,
복호화 키(개인키)는 정해진 사용자만 사용할 수 있습니다.
대칭키 방식 보다 보안에 더 안전하다는 특징이 있습니다.

### 4. SQL Injection이란 무엇인가요?
SQL Injection은 SQL문을 이용해 공격문을 주입하는 해킹 방식을 말합니다.
예를 들어, 상품 조회 URI에 'OR 1 + 1' 을 추가해 DB로 넘어가는 SQL문에 넘어가는 WHERE절을 무력화시켜 데이터를 탈취할 수  있습니다.

### 5. XSS란 무엇인가요?
Cross Site Scripting의 약자로, 사이트에 스크립트를 넣는 해킹 방식을 말합니다.
공격자가 악의적인 스크립트를 심어둔 후, 유저가 해당 스크립트를 실행하게 되면, 
공격자는 쿠키나 세션, 토큰 등의 데이터를 탈취할 수 있습니다.

### 6. CSRF란 무엇인가요?
Cross Site Request Forgery. 유저가 자신의 의지와 무관하게 공격자가 의도한 행위를 특정사이트에 요청하게 하는 공격을 말합니다.
로그인된 유저가 특정 링크를 클릭했을 때, 유저의 권한을 도용해 가짜 요청을 서버에 전송합니다.

### 7. XSS와 CSRF의 차이점
XSS는 스크립트가 실행되는 브라우저에서 탈취가 일어나며, CSRF는 서버에서 탈취가 일어납니다.
XSS는 인증된 세션이 없어도 공격할 수 있고, CSRF는 인증된 세션을 이용해서 공격을 합니다.

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

### 1. 트리 구조에 대하여 설명해주세요
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

### 1. rdbms 와 nosql 차이에 대해 설명해주세요. (키워드 : 정향화 vs 비정형화)
RDBMS는 관계형 데이터 베이스 시스템으로, 2차원의 구조화된 테이블 안에 데이터를 저장하고 관리하며, 각 vendor에 맞는 SQL 언어를 사용합니다.
NoSQL은 Not only SQL의 약자를 말하며, SQL만 사용하지 않는 저장소를 말합니다. key-value나 key-document, graph 등 다양한 형태로 저장이 가능합니다.
- RDBMS의 경우 정해진 스키마가 있기 때문에 데이터 구조가 명확하며, 각 데이터를 중복없이 저장할 수 있으나, 테이블이 많아질 수록 JOIN문이 많아지는 쿼리가 발생할 수 있고, 성능 향상을 위해서는 scale-up이 불가피하며, 스키마로 인해 데이터가 유연하지 않다는 단점을 가지고 있습니다.
- NoSQL의 경우 스키마 규격이 정해져 있지 않아 자유로운 데이터 구조를 가질 수 있으며, scale-up 뿐 아니라, scale-out 또한 가능합니다. 저장된 데이터를 언제든 조정하고 새로운 필드를 추가할 수 있다는 장점을 가지고 있습니다.
하지만 데이터 중복이 발생할 수 있고, 명확한 구조가 정해져 있지 않기 때문에 데이터 구조를 결정하기 어려울 수 있습니다.
- RDBMS는 데이터 구조가 명백하여 변경될 여지가 없는 경우에 사용하는 것이 좋고, NoSQL의 경우 정확한 데이터 구조를 알 수 없고, 변경 및 확장될 가능성이 높은 경우에 사용하는 것이 좋습니다.
rf. scale-out은 하나의 장비에서 처리하는 걸 여러 장비로 나누는 것(=서버 노드 대수를 나눈다), scale-up은 하드웨어 장비의 성능을 높이는 것(CPU를 변경하거나, 더 빠른 RAM 추가 등)
rf. <a href= "https://khj93.tistory.com/entry/Database-RDBMS%EC%99%80-NOSQL-%EC%B0%A8%EC%9D%B4%EC%A0%90">RDB와 NOSQL차이점</a>

<br>

## 네트워크

### 1. HTML과 HTML5의 차이점 (키워드 : 멀티미디어/ActiveX, Geolocation, Css3)
HTML5는 HTML의 다섯번째 업그레이드 버전을 말합니다. 
멀티미디어 기능(Active X 설치 없이도 가능), 웹 저장 기능, 웹 소켓 기능, 위치(GeoLocation) 기능, CSS3 이 추가되었습니다.

<br>

### 2. GET과 POST의 차이점 (키워드 : 조회, 등록/수정, 멱등)
GET은  서버의 데이터를 조회하기 위해 사용하는 메소드로, 일반적으로 쿼리 스트링을 통해 데이터를 전송하며, 길이 제한이 있습니다. 
보안이 필요한 데이터는 쿼리 스트링에 노출하지 말아야 합니다.
POST는 서버에 데이터를 생성하거나 수정하기 위해 사용하는 메소드로, body에 데이터를 담아 전송하며, 보안적인 측면에서 GET보다는 안정성이 있습니다. 
+ GET은 멱등하고, POST는 멱등하지 않습니다.
ㄴ 멱등이란? 연산을 여러번 적용해도 동일한 결과가 나오는 것
ㄴ GET은 조회만 하기 때문에 여러 번 날려도 동일한 결과가 나오지만, POST는 저장 및 수정에 관한 메소드기 때문에 항상 동일한 결과가 나오지는 않습니다.

<br>

### 3. TCP와 UDP의 차이점 (키워드: 연결형/비연결형 데이터 전송 프로토콜)
TCP와 UDP는 데이터를 전송할 때 사용하는 프로토콜입니다.
TCP는 연결형으로, 3-way handshake를 통해 신뢰성을 보장하지만, 일반적으로 UDP 보다 전송 속도가 느리다는 단점이 있습니다. 
따라서, 파일 전송과 같이 신뢰성이 필요한 경우에 사용합니다.
UDP는 비연결형으로, 전송 순서가 바뀔 수 있으며, 신뢰성이 낮은 대신 속도가 빠르다는 장점을 가지고 있습니다.
따라서, 스트리밍과 같이 신뢰성은 떨어지더라도 서비스의 연속성이 중요한 곳에 사용됩니다. 
+ TCP는 헤더의 용량이 UDP 보다 더 큽니다. (속도가 따라서 UDP가 더 빠릅니다.)
+ 3-way handshake : (1) 데이터 보내요? (클라이언트 -> 서버), (2) OK! (서버 -> 클라이언트), (3) 보내요 이제~ (클라이언트 -> 서버)

<br>

### 4. HTTP와 HTTPS의 차이 (키워드 : 요청/응답 프로토콜, 암호화된 데이터)
HTTP는 데이터의 요청/응답 시 사용되는 프로토콜을 말합니다. 암호화되지 않은 평문 데이터를 전송하기 때문에 서버와 주고 받는 데이터를 볼 수 있습니다. (80포트 사용)
HTTPS는 HTTP에 SSL를 추가한 것으로, HTTP에서 데이터 암호화가 추가된 것을 말합니다. HTTPS는 암호화된 데이터를 전송하기 때문에 제 3자가 데이터를 볼 수 없습니다. (443포트 사용)
+ HTTPS의 암호화 방식 : (1) 대칭키 암호화 방식 (2) 비대칭키 암호화 방식
ㄴ (1) 대칭키 암호화 : 클라이언트, 서버가 동일한 키를 사용해 암호화/복호화
ㄴ (2) 비대칭키 암호화 : 공개키와 개인키를 사용해 암호화/복호화

<br>

### 5. RESTful API란 무엇인가요?
REST한 API를 Restful API라고 합니다.
REST는 아키텍처의 한 형태를 말하는 것으로, HTTP Method를 통해 Json/Html/Xml과 같은 형태로 데이터를 주고 받는 것을 말합니다.
성능의 향상 보다는 개발자간의 규칙을 통해 API 이해도와 호환성을 높이기 위해 사용합니다. (유지보수와 코드 재사용성)

<br>

### 6. 동기와 비동기 방식의 차이점 (작업 순서 보장)
동기는 요청을 하고 결과가 나올 때까지 기다리지만(작업 순서 보장), 비동기는 요청을 하고 결과가 오지 않아도 다음 요청을 진행합니다.(작업 순서 보장X)
동기는 여러 요청을 동시에 처리할 수 없으며(ex. 1:1), Blocking 방식(하나의 작업이 끝날 때까지는 잠시 멈춰 있는 상태)입니다.
비동기는 여러 요청을 동시에 처리하며(ex. 1:N), Non-Blocking 방식입니다.

<br>

### 7. 프록시 서버란 무엇이고 어떤 역할을 하나요?
프록시 서버는 유저를 대신해서 데이터를 가져오는 서버를 말합니다. (클라이언트 -> 프록시 서버 -> 인터넷 서버)
프록시 서버를 사용하는 이유는 (1) 캐시 데이터를 활용하기 위해서, (2) 보안 때문에 사용합니다.
프록시 서버에 한 번 데이터를 캐싱하면 다른 유저가 접속했을 때 다시 DB를 거치지 않아도 데이터를 사용할 수 있게 됩니다.
더불어, 프록시 서버를 통해 중간 경유를 할 경우 유저의 IP를 노출하지 않아도 되기 때문에 방화벽 목적으로 프록시 서버를 사용하기도 합니다.
<br>
* 프록시(Proxy)는 대리라는 뜻

<br>

### 8. DNS란?
DNS란, Domain naming server를 말하며, 도메인 이름과 IP 주소를 상호 변환해주는 것을 말합니다.

<br>

### 9. 패킷이란?
패키지와 버킷의 합성어로 데이터의 전송 단위를 말합니다. (데이터의 전송 기본 단위)

<br>

### 10. 쿠키와 세션의 차이는?
쿠키는 브라우저 로컬에 저장되는 key-value 형태의 데이터 파일을 말합니다.
세션은 브라우저가 종료되기 전까지 유저의 요청을 유지하게 해주는 기술을 말합니다.
(저장위치)쿠키는 로컬에 저장하지만, 세션은 로컬과 서버에 저장하며,
(생명주기)쿠키는 브라우저를 종료해도 파일로 남아있지만, 세션은 브라우저 종료시 삭제됩니다.
(속도)쿠키는 파일에서 읽기 때문에 상대적으로 빠릅니다. 하지만 세션은 요청때마다 서버에서 처리를 해야하기 때문에 상대적으로 느립니다.

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
프로세스는 운영체제로부터 각각 독립된 영역인 Code/Data/Stack/Heap을 할당받으며, 하나의 프로세스 안에는 하나의 쓰레드가 생성됩니다.
쓰레드는 프로세스 내에서 동작되는 실행의 흐름으로, 각각 Stack만 따로 할당받고, Code/Data/Heap영역은 공유합니다.

<br>

### 5. 컨텍스트 스위칭에 대해 말해보세요. (작업의 변화, 프로세스 컨택스트를 교체)
하나의 프로세스가 실행되고 있는 상태에서 다른 우선순위의 요청이 들어왔을 때, 기존의 컨텍스트를 저장하고, 다음 프로세스를 실행할 수 있도록 새로운 컨텍스트로 교체하는 작업
<br> 
* 컨텍스트란 프로세스를 실행하기 위한 정보를 말한다.
<br>
* CPU는 한 번에 하나의 작업만 가능하기 때문에 여러 프로세를 돌아가면서 처리를 하는데 이 때 사용하는 것이 컨텍스트 스위칭입니다.
<br>
* 컨텍스트 스위칭의 종류 : (1) 프로세스의 컨택스트 스위칭, (2) 쓰레드의 컨택스트 스위칭
<br>
* ㄴ 프로세스의 컨텍스트 스위칭의 경우, 공유되는 영역이 없으므로, 컨택스트 스위칭의 시간이 더 오래 걸리지만, 
<br>
* ㄴ 쓰레드의 컨텍스트 스위칭의 경우, 공유 영역이 많기 때문에, 컨택스트 스위칭이 프로세스보다 빠릅니다.

<br>

### 6. 힙 영역과 스택 영역의 차이점은?
힙 영역은 런타임에 사용자에 의해 동적으로 할당되는 메모리 영역으로, 전역 변수가 저장되는 공간입니다. (ex. 객체 인스턴스)
스택 영역은 함수가 호출 될 때 LIFO 방식으로 쌓이는 메모리 영역으로, 지역변수와 매개변수가 저장되는 공간입니다.
<br>
* 코드 영역(코드), 데이터 영역(전역 변수와 정적 변수), 스택 영역(지역 변수, 매개변수/ 정적 메모리가 저장되며 LIFO 방식), 힙 영역(전역 변수/ 동적 할당)

### 7. 프로세스 간의 통신과 쓰레드 간의 통신에 대해 비교해서 설명하세요. (통신 기술의 필요 유무)
프로세스 간에는 서로 주소 공간이 분리되어 있어, IPC(Inter-Process Communication)를 통해 소통을 합니다.
반면, 쓰레드 간에는 서로 하나의 프로세스 주소 공간 안에서 코드/데이터/힙 공간을 공유하기 때문에 별도의 통신 기술이 필요하지 않습니다.

<br>

### 8. 멀티 쓰레드와 멀티 프로세스의 차이점에 대해 말하고, 둘을 언제 써야 하는지 말해보세요.
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
