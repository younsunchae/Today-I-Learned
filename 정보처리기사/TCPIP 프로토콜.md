# 전송 계층 프로토콜

### 1. TCP(Transmission Control Protocol)

- 양방향 연결형 서비스를 제공
- 가상 회선 연결 형태의 서비스를 제공
- 스트림 위주의 전달
- 신뢰성 있는 경로를 확립하고 메세지 전송을 감독
- 순서 오류 흐름 제어 기능
- 투명성이 보장되는 통신을 제공

### 2. UDP(User Datagram Protocol)

- 비연결형 서비스
- TCP에 비해 단순한 헤더 구조
- 실시간 전송에 유리

### 3. RTCP(Real-Time Control Protocol)

- RTP 패킷의 전송 품질을 제어하기 위한 제어 프로토콜
- 세션에 참여한 각 참여자들에게 주기적으로 제어정보를 전송

# 인터넷 계층의 주요 프로토콜

### 1. IP(Internet Protocol)

- 전송할 데이터에 주소를 지정하고 경로를 설정하는 긴으
- 비연결형인 데이터그램 방식을 사용하는 것을 신뢰성이 보장되지 않음

### 2. ICMP(Internet Control Message Protocol) 제어 메시지 프로토콜

- IP에 조합하여 통신중에 발생하는 오류의 처리와 전송 경로 변경등을 위한 제어 메세지를 관리

### 3. IGMP(Internet Group Management Protocol) 인터넷 그룹 관리 프로토콜

- 멀티캐스트를 지원하는 호스트나 라우터 사이에서 멀티캐스트 그룹 유지를 위해 사용

### 4. ARP(Address Resolution Protocol) 주소 분석 프로토콜

- 호스트이 IP 주소를 호스트와 연결된 네트워크 접속 장치의 물리적 주소로 바꿈

### 5. RARP(Reverse Address Resolution Protocol)

- ARP와 반대로 물리적 주소를 IP 주소로 변환

# 네트워크 액세스 계층의 주요 프로토콜

### 1. Ethernet(IEEE 802.3)

- CSMA/CD 방식의 LAN

### 2. IEEE 802

- LAN을 위한 표준 프로토콜

### 3. HDLC

- 비트 위주의 데이터 링크 제어 프로토콜

### 4. X.25

- 패킷 교환망을 통한 인터페이스를 제공하는 프로토콜

### 5. RS-232C

- 공중 전화 교환망을 통한 인터페이스를 제공하는 프로토콜
