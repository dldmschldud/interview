## OSI 7 layer

OSI - Open Systems Interconnection

ISO - International Standards Organization

과거에는 통신용 규약이 표준화되지 않았기 때문에 호환되지 않는 시스템이나 애플리케이션이 많았고 통신이 불가능했다. 

이를 하나의 규약으로 통합하려는 노력이 현재의 OSI7계층에 남아있다. 

OSI7 계층은 네트워크 동작을 나누어 이해하고 개발하는데 많은 도움이 되기 때문에 네트워크 주요 참조(레퍼런스) 모델로 활용되고 있지만 현재는 대부분의 프로토콜이 TCP/IP 프롵토콜 스택 기반이다. 

복잡한 데이터 전송 과정을 OSI 7 계층으로 나눠서 보면 이해하기 쉽고 계층별로 프로토콜을 개발해 네트워크 구성 요소들을 모듈화할수 있다.

Layer 1-4 = 데이터 플로 계층 / 하위 계층

Layer 5-7 = 애플리케이션 계층 / 상위 계층

#### 7. Application

Protocol Data Unit = Data

사용자가 특정 어플리케이션을 이용해서 데이터를 이용하고 가공한다

#### 6. Presentation 

Protocol Data Unit = Data

encoding, encryption, compress

누구나 알수 있는데이터의 형태로 보내고 

#### 5. Session 

Protocol Data Unit = Data

연결

쌍방으로 동시에 주고받을지, 일방적으로 받기만 할지, 번갈아가며 주고받을지와 같은 회선의 생성, 유지, 종료에 대한 관리

#### 4. Transport 

Protocol Data Unit = Segments

tcp, udp

#### 3. Network

Protocol Data Unit = Packets

ip

#### 2. Data Link

Protocol Data Unit = Frames

mac 

#### 1. Physical 

Protocol Data Unit = Bits

물리적 연결과 관련된 정보를 정의

전기 신호가 물리계층 장비에 들어오면 이 전기 신호를 재생성하여 내보낸다 (물리계층 장비는 주소 개념이 없기때문에 전기 신호가 들어온 포트를 제외한 모든 포트에 같은 전기 신호를 전송)

물리 계층은 한 네트워크 노드에서 다른 네트워크 노드로 케이블을 통해 데이터를 전송하며 상위 계층은 물리계층에서 전송되는 비트에 의미를 할당한다

물리계층 주요 장비 - 허브, 리피터, 케이블, 커넥터, 트랜시버, 탭

![7layers](../images/7layers.png)
