# Chapter 1 네트워크 퀴즈 답안 및 해설

## 1. 네트워크 프로토콜에 의해 정의되지 않는 것은?

**답: b) Content (Payload)**

**해설:**

- 네트워크 프로토콜은 데이터의 **형식(Format)**, **순서(Order)**, **동작(Actions)**을 정의합니다
- 하지만 **내용(Payload)**은 프로토콜이 정의하지 않습니다. 페이로드는 사용자가 전송하고자 하는 실제 데이터로, 프로토콜은 이를 어떻게 전송할지만 정의합니다

---

## 2. 인터넷에 대한 잘못된 설명은?

**답: d) 인터넷은 전 세계적으로 하나의 조직이 소유하고 관리하는 단일 네트워크이다**

**해설:**

- 인터넷은 수십억 개의 연결된 컴퓨팅 장치들의 모음입니다 (a번 맞음)
- 통신 링크와 패킷 스위치로 구성되어 있습니다 (b번 맞음)
- 웹, 이메일, 스트리밍 비디오 등의 서비스를 제공합니다 (c번 맞음)
- 하지만 인터넷은 **여러 ISP와 조직들이 협력하여 운영하는 분산 시스템**입니다

---

## 3. 중앙 사무소에서 가정까지 광섬유 경로를 제공하는 것은?

**답: b) FTTH (Fiber To The Home)**

**해설:**

- **FTTH**: Fiber To The Home - 가정까지 직접 광섬유를 연결하는 기술
- DSL: 기존 전화선을 이용한 인터넷 서비스
- Satellite: 위성을 이용한 인터넷 서비스
- LTE: 무선 이동통신 기술

---

## 4. 메시지를 작은 패킷으로 나누어 독립적으로 라우팅하고 목적지에서 재조립하는 데이터 전송 방법은?

**답: Packet switching (패킷 스위칭)**

**해설:**

- 패킷 스위칭은 데이터를 작은 패킷으로 분할하여 각각 독립적으로 전송하는 방식입니다
- 각 패킷은 헤더에 목적지 정보를 포함하고 있어 독립적으로 라우팅됩니다
- 목적지에서 원래 순서대로 재조립됩니다

---

## 5. 네트워크 코어의 주요 기능은?

**답: a) Routing, c) Forwarding**

**해설:**

- **Routing**: 패킷이 목적지까지 가는 최적의 경로를 결정
- **Forwarding**: 패킷을 적절한 출력 포트로 전달
- Multiplexing, Loss Recovery, Security는 네트워크 코어의 핵심 기능이 아닙니다

---

## 6. 키워드 매칭

**답:**

- a) Network edge → 2) Data Center
- b) Access networks → 1) WiFi
- c) Physical media → 4) Wireless Radio
- d) Network core → 3) Router

**해설:**

- Network edge: 데이터 센터가 위치하는 네트워크의 가장자리
- Access networks: WiFi 등 사용자가 네트워크에 접근하는 기술
- Physical media: 무선 라디오 등 실제 전송 매체
- Network core: 라우터가 위치하는 네트워크의 중심부

---

## 7. 패킷 스위칭에 대한 올바른 설명은?

**답: b) 자원이 공유되어 더 많은 사용자가 네트워크를 활용할 수 있다**

**해설:**

- 패킷 스위칭에서는 각 패킷이 독립적으로 라우팅되므로 같은 경로를 따를 필요가 없습니다 (a번 틀림)
- 자원 공유를 통해 효율적인 네트워크 활용이 가능합니다 (b번 맞음)
- 연결 설정 없이도 패킷 전송이 가능합니다 (c번 틀림)
- 버스트성 데이터도 효율적으로 처리할 수 있습니다 (d번 틀림)

---

## 8. YouTube 접속 문제 해결 순서는?

**답: b → a → d → c**

**해설:**

1. **스마트폰 (b)**: 가장 가까운 디바이스부터 확인
2. **HGU_WLAN (a)**: WiFi 연결 상태 확인
3. **KT ISP (d)**: 인터넷 서비스 제공업체 연결 확인
4. **YouTube (c)**: 마지막으로 콘텐츠 제공업체 확인

---

## 9. 패킷 지연 유형과 설명 매칭

**답:**

- a) → 3) Transmission delay
- b) → 1) Queueing delay
- c) → 2) Processing delay
- d) → 4) Propagation delay

**해설:**

- **Transmission delay**: 패킷의 모든 비트를 링크로 밀어넣는 시간
- **Queueing delay**: 출력 버퍼에서 전송 대기 시간
- **Processing delay**: 비트 오류 검사 및 출력 링크 결정 시간
- **Propagation delay**: 물리적 링크를 통한 비트 전파 시간

---

## 10. Traceroute에서 11번째 홉이 10번째 홉보다 지연이 적은 이유는?

**답: b) Queueing delay**

**해설:**

- 11번째 홉에서 큐잉 지연이 감소했을 가능성이 높습니다
- 네트워크 혼잡도가 일시적으로 감소하거나, 해당 라우터의 트래픽이 줄어들었을 수 있습니다
- 거리가 멀어져도 큐잉 지연이 줄어들면 전체 지연이 감소할 수 있습니다

---

## 11. Rs=100Mbps, Rc=60Mbps, R=300Mbps일 때 최대 처리량과 병목은?

**답: c) Throughput=60Mbps, Bottleneck=Client-side links**

**해설:**

- 4개의 서버-클라이언트 쌍이 공유 중간 링크(R=300Mbps)를 사용
- 공유 링크는 300/4 = 75Mbps씩 할당 가능
- 하지만 클라이언트 측 링크(Rc=60Mbps)가 더 제한적
- 따라서 최대 처리량은 60Mbps이고, 클라이언트 측 링크가 병목입니다

---

## 12. 패킷 지연과 패킷 손실에 대한 올바른 설명은?

**답: b) 큐잉 지연은 트래픽 강도(La/R)가 1에 접근할수록 증가한다**

**해설:**

- 트래픽 강도가 1에 가까워질수록 큐가 가득 차게 되어 큐잉 지연이 급격히 증가합니다
- 패킷 손실은 전송 지연과 직접적인 관련이 없습니다 (a번 틀림)
- 전파 지연은 거리와 전파 속도에만 의존합니다 (c번 틀림)
- 라우터는 큐가 가득 차면 패킷을 드롭할 수 있습니다 (d번 틀림)

---

## 13. 하위 계층 프로토콜이 상위 계층으로부터 데이터를 받아 자신의 헤더를 추가하여 PDU를 형성하는 과정은?

**답: Encapsulation (캡슐화)**

**해설:**

- 캡슐화는 각 계층에서 데이터에 헤더나 트레일러를 추가하는 과정입니다
- 하위 계층으로 갈수록 더 많은 헤더가 추가됩니다
- 이를 통해 계층별 기능(라우팅, 오류 검출, 흐름 제어 등)을 구현합니다

---

## 14. 인터넷 프로토콜 계층 순서 (사용자에 가까운 순서대로)

**답: Application → Transport → Network → Link → Physical**

**해설:**

1. **Application Layer**: 사용자와 가장 가까운 계층 (HTTP, SMTP, FTP 등)
2. **Transport Layer**: 프로세스 간 통신 (TCP, UDP)
3. **Network Layer**: 라우팅 및 논리적 주소 지정 (IP)
4. **Link Layer**: 인접 노드 간 데이터 전송 (Ethernet, WiFi)
5. **Physical Layer**: 하드웨어와 가장 가까운 계층 (전기 신호, 광 신호)

---

## 15. 인터넷 프로토콜 스택에서 전송 계층의 주요 기능은?

**답: a) 애플리케이션 간 프로세스 대 프로세스 데이터 전송**

**해설:**

- 전송 계층은 **프로세스 간 통신**을 담당합니다
- TCP/UDP를 통해 애플리케이션 간 신뢰성 있는 데이터 전송을 제공합니다
- 라우팅은 네트워크 계층의 기능입니다 (b번 틀림)
- 물리적 특성 정의는 물리 계층의 기능입니다 (c번 틀림)
- 프레임 캡슐화는 링크 계층의 기능입니다 (d번 틀림)

---

## 전체 답안 요약

1. b) Content (Payload)
2. d) The Internet is a single network owned and managed by one organization worldwide
3. b) FTTH
4. Packet switching
5. a) Routing, c) Forwarding
6. a-2, b-1, c-4, d-3
7. b) Resources are shared, allowing more users to utilize the network
8. b → a → d → c
9. a-3, b-1, c-2, d-4
10. b) Queueing delay
11. c) Throughput=60Mbps, Bottleneck=Client-side links
12. b) Queueing delay increases as the traffic intensity (La/R) approaches 1
13. Encapsulation
14. Application-Transport-Network-Link-Physical
15. a) Process-to-process data transfer between applications
