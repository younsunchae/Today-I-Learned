# IP

## 개념

- IP(Internet Protocol)은 송신 호스트와 ㅜ신 호스트가 패킷 교환 네트워크에서 정보를 주고받는 데 사용하는 정보 위주의 규약이다.
- OSI 3계층인 네트워크 계층에서 호스트의 주소 지정과 패킷 분할 및 조립 기능을 담당
- IP의 정보는 패킷 혹은 데이터그램이라고 하는 덩어리로 나위어 전송된다

## 특징

1. 비신뢰성, 비연결형

- 비신뢰성은 흐름에 관여하지 않기 때문에 보낸 정봐 제대로 갔는지 보장하지 않는다는 뜻
- 패킷 전송과 정확한 순서를 보장하려면 TCP 프로토콜과 같은 IP의 상의 프로토콜을 이용해야 함

2. 에러제어와 흐름제어가 없음

- 정보의 전송이 가장 중요하고, 보낸 정보의 내용을 보장하지 않음
- 패킷은 에러 검출만하고 만약 발견되면 폐기

3. 대표적인 IP 주소체계

- 현재 인터넷에서 사용하는 표준 프로토콜은 IPV4이고, 주소 공간ㄱ갈 문제를 겪고 있어서 IPV6가 점차 확산

4. IP 크기 제한

- IP의 크기는 20~40 바이트로 제한되어 있다.
- IP패킷은 네트워크가 수용할수 있는 크기로 분할되어야하는데 이를 `단편화`라고 한다.

# IPv4

## 개념

- IPv4는 인터넷에서 사용되는 패킷 교환 네트워크 상에서데이터를 교환하기 위한 32비트 주소체계를 갖는 네트워크 계층의 프로토콜

## 헤더

- IP 패킷의 앞부분에서 주소 등 각종 제어정보를 담고 있는 부분
- 헤더 사이즈는 옵션 미지정시 최소 20바이트 이상

## 주소체계

- 10진수로 총 12자리이며, 4 부분으로 나뉜다. <br/>
- 각 부분은 10진수 0부터 255까지 3자리의수로 표현된다.
- 32비트 IP 주소는 network를 나타내는 부분과 Host를 나타내는 부분으로 구성되어있고, Network와 Host 부분을 구분하는 것은 서브넷 마스크이다.

### CIDR (Classes Inter-Domain Routing) 기법

클래스 없는 도메인 간 라우팅 기법으로 최신의 IP 주소 할당 방식 <br/>
`(IP 주소) / (네트워크 ID 비트 수)`

## 서브네팅

- IP 주소 고갈 문제를 해결하기 위해 원본 네트워크를 여러 개의 네트워크로 분리하는 과정

### 서브네팅 종류

#### 1. FLSM(Fixed-Length Subnet Masking)

서브넷의 길이를 고정적으로 사용, 한 대역을 동일한 크기로 나누는 방식

#### 2. VLSM(Variable Length Subnet Masking)

서브넷의 길이를 가변적으로 사요ㅇ, 하나 대역을 다양한 크기로 나누는 방식

# IPv6

현재 IPv4가 가지고 있는 주소 고갈, 보안성, 이동성 지원 등의 문제점을 해결하기 위해 개발된 128bit 주소 체계를 갖는 차세대 인터넷 프로토콜

## 특징

1. IP 주소의 확장 <br/>
   IPv4의 기존 32비트 주소 공간에서 벗어나, IPv6는 128비트 주소 공간을 제공
2. 이동성 <br/>
   IPv6 호스트는 네트워크의 물리적 위치에 제한받지 않고 같은 주소를 유지하면서도 자유롭게 이동 가능
3. 인증 및 보안 기능 <br/>
4. 개선된 Qos 지원 <br/>
   흐름 레이브릉ㄹ도이브 특정 트래픽은 별도의 특별한 처리를 통해 높은 품질의 서비스를 제공
5. Plug & Play 지원
6. Ad - hoc 네트워크 지원 <br/>
   Ad - hoc 네트워크를 통한 자동 네트워킹 및 인터넷 연결 지원, 자동으로 네트워크 환경 구성이 가능
7. 단순 헤더 적용 <br/>
   IP 패킷의 처리를 신속하게 할 수 잇도록 고정 크기의 단순 헤더를 사용하는 동시에, 확장 헤더 지원
8. 실시간 패킷 추적 가능
   흐름 레이블을 사용하ㅏ여 패킷의흐름을 실시간 재공

## 헤더

기존 IPv6 헤더에 비해 IPv6 헤더가 IPv6 출발지 주소, 목적지 주소의 주소 길이로 인하여 커졌고, IPv4의 불필요한 힐드를 제거함으로써 헤더가 단순해짐

## 주소 체계

- 128비트의 주소 공간을 제공
- 16비트 단위로 나누어지며 각 16 비트 블록은 다시 4자리 16진수로 변환되고 콜론으로 구분
