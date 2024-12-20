"OSI 7 계층의 체계적인 세계로 들어가볼까요? 🏰"

1. OSI 7 Layer란?
   "네트워크 통신을 7개의 계층으로 나눈 이유가 뭘까요?"
- 국제표준화기구(ISO)에서 제정
- 통신 과정을 단계별로 나눔
- 각 계층은 독립적 역할 수행
- 복잡한 통신 과정을 모듈화! 🎯

2. 계층별 주요 기능:
   "각 계층은 어떤 역할을 할까요?"

7계층 (응용 계층):
- 사용자와 가장 가까운 계층
- HTTP, FTP, SMTP
- 최종 사용자의 인터페이스

6계층 (표현 계층):
- 데이터 형식 변환
- 암호화/복호화
- JPEG, MPEG

5계층 (세션 계층):
- 연결 세션 관리
- 동기화
- NetBIOS, RPC

4계층 (전송 계층):
- 종단간 신뢰성
- TCP, UDP
- 흐름제어, 오류제어

3계층 (네트워크 계층):
- 라우팅, 경로 설정
- IP, ICMP
- 패킷 전달

2계층 (데이터링크 계층):
- 물리적 주소 지정
- MAC 주소
- 프레임 단위 전송

1계층 (물리 계층):
- 비트 단위 전송
- 전기적, 기계적 특성
- 케이블, 허브

```text
7계층 (응용 계층):
민수가 편지를 쓰기로 결정합니다. "영희야 잘 지내니?"라는 내용을 종이에 적습니다. 이것은 사용자가 직접 상호작용하는 부분이죠.
6계층 (표현 계층):
민수가 쓴 편지를 예쁜 글씨체로 다시 쓰고, 혹시 영희만 알아볼 수 있게 둘만의 약속된 암호로 일부 내용을 바꿉니다. 마치 데이터를 암호화하고 형식을 갖추는 것처럼요.
5계층 (세션 계층):
편지를 주고받는 동안 서로 연락이 끊기지 않도록 관리합니다. 예를 들어 "답장 기다릴게"라고 쓰거나, 편지 번호를 매기는 것처럼요.
4계층 (전송 계층):
편지가 안전하게 배달되도록 보장합니다. 등기우편을 사용하거나, 중요한 내용이라 "잘 받았는지 문자 줘"라고 메모를 남기는 것과 같습니다.
3계층 (네트워크 계층):
어떤 경로로 편지를 보낼지 결정합니다. 서울에서 부산으로 갈 때 어느 지역을 거쳐 가야 할지 우체국에서 경로를 정하는 것과 같죠.
2계층 (데이터링크 계층):
실제 배송을 위해 주소를 확인하고 편지봉투에 보내는 사람과 받는 사람의 주소를 정확히 기재합니다. 우편번호와 같은 정확한 주소 체계를 사용하는 거죠.
1계층 (물리 계층):
실제로 편지를 운반하는 과정입니다. 우체부가 우체통에서 편지를 수거하고, 트럭으로 운반하고, 최종적으로 영희의 집 우편함에 배달하는 물리적인 과정이죠.
```

3. 데이터 전달 과정:
   "데이터는 어떻게 이동할까요?"

캡슐화 (하향식):
- 각 계층마다 헤더 추가
- 7계층 → 1계층
- 데이터 → 패킷 → 프레임

역캡슐화 (상향식):
- 각 계층마다 헤더 제거
- 1계층 → 7계층
- 프레임 → 패킷 → 데이터

4. 계층별 PDU(Protocol Data Unit):
   "각 계층의 데이터 단위는?"
- 7-5계층: 데이터
- 4계층: 세그먼트
- 3계층: 패킷
- 2계층: 프레임
- 1계층: 비트

5. OSI 모델의 장점:
   "이렇게 나누면 뭐가 좋을까요?"

👍 장점:
- 표준화된 컴포넌트
- 호환성 보장
- 모듈식 엔지니어링
- 쉬운 문제 해결

⚠️ 단점:
- 실제와 차이 있음
- 계층간 중복 기능
- 복잡한 구조

자주 나오는 꼬리 질문! 🤔

Q1: "TCP/IP 모델과 OSI 모델의 차이점은?"
A1: TCP/IP는 실제 구현된 프로토콜 스택으로, 4계층으로 구성되어 있어요.
OSI는 참조 모델로, 더 세분화된 7계층 구조를 가지고 있죠.
실무에서는 TCP/IP를 많이 사용한답니다!

Q2: "각 계층을 대표하는 장비는?"
A2: 7-5계층: 게이트웨이
4계층: L4 스위치
3계층: 라우터
2계층: L2 스위치
1계층: 허브, 리피터

핵심 포인트! 💡
1. "계층별 역할 명확히 구분"
2. "독립성과 유연성 보장"
3. "표준화된 인터페이스"
4. "문제 해결 용이"
5. "모듈화된 설계 가능"


![img.png](7Layer(1).png)


![img_1.png](7Layer(2).png)


![img_2.png](7Layer(3).png)
