# Network
## Contents


- [컴퓨터 네트워킹과 인터넷의 역사](#컴퓨터-네트워킹과-인터넷의-역사)
- [인터넷](#인터넷)
- [프로토콜](#프로토콜)
- [인터넷 프로토콜 스택](#인터넷-프로토콜-스택)
- [네트워크 애플리케이션](#네트워크-애플리케이션)
- [HTTP](#HTTP)
- [Mac 주소](#Mac-주소)
- [네트워크 인터페이스 카드](#네트워크-인터페이스-카드)


## 컴퓨터 네트워킹과 인터넷의 역사
컴퓨터 네트워킹과 오늘날 인터넷 분야의 시작은 1960년대 초로 거슬러 올라가는데 이 시기의 주요 통신 네트워크는 전화망이었고 전화망이 송신자에서 수신자로 정보를 전송하는데 회선교환을 사용했다.

1960년대 초 컴퓨터 사용이 증가하면서 회선 교환을 대신할수 있는 효울적이고 견실한 방법으로 패킷 교환의 개념이 창안되었다.

1969년 첫번째 패킷 교환 컴퓨터 네트워크이자 오늘날 공중 인터넷의 직계원조인 ARPANET이 시작되었다

1972년 ARPANET 종단 시스템간의 NCP(network control protocol)라는 host-to-host프로토콜이 완성되었고 종단간에서 프로토콜을 사용할수 있게되자 애플리케이션 개발을 할수 있게 되었다

1970년대 중반 초 ARPANET과 별개의 패킷 교환 네트워크들이 많이 생겨났고 네트워크의 수가 증가함에 따라 네트워크를 연결하는 포괄 구조의 개발이 필요하게 돼 상호연결 네트워크(네트워크의 네트워크)를 위한 노력이 이루어졌다

네트워크이 네트워크는 TCP프로토콜로 구체화 되었는데 TCP초기 버전은 지금의 TCP와는 매우 다르다

초기 버전의 TCP = 종단 시스템의 재전송을 통한 데이터의 신뢰적 전송 + 전달기능(오늘날 IP가 수행하는 기능) 

비신뢰적이고 흐름제어가 없는 종단간의 전송 서비스의 중요성으로 인해 TCP에서 IP를 분리하여 UDP 프로토콜을 개발하게 됐다

TCP, UDP, IP같은 주요 인터넷 프로토콜은  1970년대 후반에 개념이 자리 잡았다.

1983년 ARPANET의 새로운 표준 호스트 프로토콜인 TCP/IP가 공식 설치되었다

1980년대 후반 호스트기반 혼잡제어 구축을 위해 TCP에 중요한 확장이 이루어졌으며 DNS도 개발됐다

1990년대는 인터넷의 지속 발전과 상업화를 상징하는 두 사건으로 대변되다

1. ARPANET이 더 이상 존재하지 않게 되었다.
2. 월드 와이드 웹의 출현

웹은 하이퍼텍스트에 관한 초기 연구의 아이디어를 바탕으로한다.

## 인터넷
전 세계적으로 컴퓨팅 장치를 연결하는 컴퓨터 네트워크

world wide web은 인터넷과 다르며, 인터넷을 기반으로 한 수많은 응용 프로그램 중 하나이다.

## 프로토콜
둘 이상의 통신 개체간에 교환되는 메시지 포맷과 순서뿐 아니라, 메시지의 송수신과 다른 이벤트에 따른 행동을 정의한것 
  

## 인터넷 프로토콜 스택
프로토콜 계층은 소프트웨어, 하드웨어 또는 둘의 통합으로 구현할수 있다

다양한 계층의 프로토콜을 모두 합하여 프로토콜 스택이라고 하며, 인터넷 프로토콜 스택은 5개 계층으로 구성된다

프로토콜 계층화의 장점 -  시스템 구성요소의 갱신이 쉽다

프로토콜 계층화의 잠재된 결점 - 한계층의 기능이 하위 계층과 기능적으로 중복된다, 한 계층에서의 기능이 다른 계층에서만 존재하는 정보(타임 스탬프값) 를 필요로 할 수 있다


![ips](../images/ips.png)   

#### <애플리케이션 계층>

* 네트워크 애플리케이션을 지원

네트워크 애플리케이션과 애플리케이션 계층 프로토콜이 존재

인터넷의 애플리케이션 계층은 http(웹 문서 요청과 전송), smtp(전자메일 전송), ftp(두 종단 시스템 간의 파일 전송) 같은 프로토콜을 포함한다

애플리케이션 계층 프로토콜은 여러 종단 시스템에 분산되어 있어서, 한 종단 시스템에 있는 애플리케이션이 다른 종단 시스템에 있는 애플리케이션과 정보 패킷을 교환할때 애플리케이션 계층 프로토콜을 사용한다

애플리케이션 계층 정보 패킷 - 메시지

#### <트랜스포트 계층>

* 프로세스간 데이터 전송

클라이언트와 서버간에 애플리케이션 계층 메시지를 전송하는 서비스를 제공

인터넷의 tcp, udp(트랜스포트 프로토콜)로 애플리케이션 계층 메시지를 전달

트랜스포트 계층 패킷 - 세그먼트(segment)

#### <네트워크 계층>

* 출발지에서 목적지 까지 데이터그램을 라우팅

인터넷의 네트워크 계층은 한 호스트에서 다른 호스트로 데이터 그램을 라우팅한다

출발지 호스트에서 인터넷 트랜스포트 계층 프로토콜은 세그먼트와 목적지 주소를 네트워크 계층으로 전달하며 네트워크 계층은 목적지 호스트의 트랜스포트 계층으로 세그먼트를 운반한다

네트워크 계층의 프로토콜 - ip프로토콜, 라우팅 프로토콜

* ip프로토콜   
ip 데이터그램의 필드를 정의하며, 종단 시스템과 라우터가 이 필드에 어떻게 동작하는지 정의

* 라우팅 프로토콜    
출발지와 목적지 사이에서 데이터그램이 이동하는 경로를 결정

#### <링크 계층>

* 이웃한 네트워크 구성 요소들간의 데이터 전송

인터넷의 네트워크 계층은 출발지와 목적지 간 일련의 라우터를 통해 데이터그램을 라우트하는데 경로상의 한 노드(호스트,라우터)에서 다른 노드로 패킷을 이동하기 위해 네트워크 계층은 링크계층 서비스에 의존한다 - 각 노드에서 네트워크 계층은 데이터그램을 아래 링크 계층으로 보내고 링크 계층은 그 데이터그램을 경로상의 다음 노드에 전달하며 다음 노드에서 링크 계층은 그 데이터그램을 상위 네트워크 계층으로 보낸다

링크 계층의 프로토콜 - 이더넷, 와이파이

링크 계층의 패킷 - 프레임


#### <물리 계층>

* 전송매체 위의 비트

프레임 내부의 각 비트를 한 노드에서 다음 노드로 이동하는것

물리 계층의 프로토콜들은 링크에 의존하고 더 나아가 링크의 실제 전송매체에 의존한다

이더넷은 꼬임쌍선을 위한것, 동축케이블을 위한것등 여러가지 물리계층 프로토콜을 가지고 있다


## 네트워크 애플리케이션

* 네트워크 애플리케이션 개발의 핵심 - 다른 종단 시스템에서 동작하고 네트워크를 통해 서로 통신하는 프로그램을 작성하는것

* 여러 종단 시스템에서 동작하는 소프트웨어를 작성하기 - 네트워크 코어 장비에서 실행되는 소프트웨어를 작성할 필요없음 

* 종단 시스템에서만 애플리케이션 소프트웨어가 존재한다는 기본 설계는 인터넷 애플리케이션의 광대하고 빠른 발전의 원동력이 됨

#### <네트워크 애플리케이션 구조>

애플리케이션 구조는 인터넷 프로토콜 스택 구조와 다르다, 네트워크 구조는 고정되어있고 애플리이션 구조는 애플리케이션 개발자에 의해 설계되고 애플리케이션이 다양한 종단 시스템에서 어떻게 조직되어야 하는지를 지시한다. 

네트워크 애플리케이션에 사용되는 구조에는 클라이언트-서버 구조와 p2p구조가 있다.

1) 클라이언트-서버 구조
서버 - 항상 켜져있는 호스트로 클라이언트의 요청을 받는다

클라이언트-서버 구조에서 클라이언트는 서로 직접적으로 통신하지 않는다

서버는 고정 ip주소라는 잘 알려진 주소를 갖는다

하나의 서버 호스트가 자신의 클라이언트로부터의 모든 요청에 응답하는것이 불가능하기 때문에 데이터 센터를 사용해 강역한 가상의 서버를 생성한다


2) p2p구조

피어(peer)라는 간헌절으로 연결된 호스트 쌍이 서로 직접 통신한다

피어는 사용자들이 제어하는 데스크톱, 노트북이다(서비스 제공자가 소유하지 않음)

특정 서버를 통하지 않고 피어가 통신한다

p2p구조는 자가 확장성을 가지지만 고도의 분산 구조 특성으로 인해 보안, 성능, 신뢰성에 문제가 있다

#### <프로세스 간 통신>

실제 통신하는것은 프로그램이 아닌 프로세스로 프로세스는 종단 시스템에서 실행되는 프로그램이다

2개의 다른 종단 시스템에서 프로세스는 컴퓨터 네트워크를 통한 메시지 교환으로 통신한다

네트워크 애플리케이션은 네트워크에서 서로 메시지를 보내는 두 프로세스로 구성되는데 통신하는 프로세스 각 쌍에 대해 일반적으로 클라이언트 프로세스, 서버 프로세스라고 한다

프로세스는 소켓을 통해 네트워크로 메시지를 보내고 받는다

소켓은 호스트의 애플리케이션 계층과 트랜스포트 계층간의 인터페이스이다

소켓은 애플리케이션과 네트워크 사이의 API다

#### <애플리케이션 계층 프로토콜>

애플리케이션 계층 프로토콜은 다른 종단 시스템에서 실행되는 애플리케이션의 프로세스가 서로 메시지를 보내는 방법을 정의한다

* 교환 메시지 타입
* 여러 메시지 타입의 문법
* 필드의 의미(필드의 정보의 의미)
* 언제, 어떻게 프로세스가 메시지를 전송하고 메시지에 응답하는지 결정하는 규칙

네트워크 애플리케이션과 애플리케이션 계층 프로토콜을 구별하는것은 중요하다 - 애플리케이션 계층 프로토콜은 네트워크 애플리케이션의 한 요소다

EX) 웹 - 네트워크 애플리케이션

웹 애플리케이션은 HTML, 웹 브라우저, 웹 서버, 애플리케이션 계층 프로토콜등 여러 요소로 구성된다.
웹 애플리케이션 계층 프로토콜인 HTTP는 브라우저와 웹 서버 사이에서 교환되는 메시지의 포맷과 순서를 결정하지만 단지 웹 애플리케이션의 한 요소다


## HTTP
  
transport layer security

메시지를 보호할수 있게 상대방과 약속한 통신 규약

두 사람이 서로 통신할때, 제 삼자가 가운데에서 두 사람의 통신 내용을 도청한다고 해도 안전하게 통신의 내용을 보호할수 있게 하는 기술

통신 당사자 간에 암호 해독을 위한 키 교환후 암호화된 메시지를 전송한다

키 교환 알고리즘 - 어떻게 암호를 해독할 키를 제 삼자의 도청하에 전달할지

해시 알고리즘 - 메시지의 무결성을 확인

인증 - 상대방의 신분을 확인

사이퍼수트 - 어떤 키 교환 알고리즘과 어떤암호화, 복호화, 인증, 해시 기술을 쓸지 정해둔것

tls에서는 사용할 사이퍼 수트를 정한 후, 상대방의 신원을 확인하고, 암호화와 복호화를 할 키를 교환한뒤 이 키를 바탕으로 암호화한 메시지를 서로 교환하며 이 메시지를 해시를 통해서 변조되지 않았음을 확인한다

## Mac 주소

Media Access Control Address

실제 장치간 통신에 사용하는 주소

ARP프로토콜을 통해 IP주소가 할당된 장치의 MAC주소를 알아낸다

## 네트워크 인터페이스 카드

= 랜카드

pc나 서버에서 네트워크를 연결해주는 카드나 인터페이스를 지칭

<네트워크 인터페이스 카드 동작 방식>

1. 전기 신호를 데이터 형태로 만든다.
2. 목적지 MAC주소와 출발지 MAC주소를 확인한다.
3. 네트워크 인터페이스 카드의 MAC주소를 확인한다.
4. 목적지 MAC주소와 네트워크 인터페이스 카드가 갖고 있는 MAC주소가 다르면 데이터를 폐기한다.
5. 목적지 MAC주소와 네트워크 인터페이스 카드가 갖고 있는 MAC주소가 같으면 데이터를 상위계층에서 처리할 수 있도록 메모리에 적재한다.


