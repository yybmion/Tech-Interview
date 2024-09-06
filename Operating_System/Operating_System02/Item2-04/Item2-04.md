# 문맥 교환(Context switch)에 대해서 설명해주세요.

1. **문맥 교환의 정의**:
    - **현재 실행 중인 프로세스의 상태를 저장**하고 다음 실행할 프로세스의 상태를 `복원`하는 과정이다.
    - CPU를 **한 프로세스에서 다른 프로세스로 전환하는 작업**이다.
    - `멀티태스킹` 운영체제의 핵심 기능 중 하나이다.


2. **문맥 교환이 발생하는 상황**:
    - **인터럽트** 발생 시
    - 현재 프로세스의 CPU **시간 할당량 만료** 시
    - I/O 요청으로 인해 프로세스가 **대기 상태로 전환**될 때
    - **높은 우선순위의 프로세스가 실행 준비**될 때


3. **문맥 교환의 과정**:
    - 현재 **프로세스의 상태 저장** (PCB에 저장)
    - **다음 실행할 프로세스 선택** (스케줄러에 의해)
    - 선택된 프로세스의 **상태 복원**


4. **저장/복원되는 정보**:
    - **프로그램 카운터**
    - **레지스터 값들**
    - **메모리 관리 정보 (페이지 테이블 등)**
    - **I/O 상태 정보**


5. **문맥 교환의 오버헤드**:
    - **CPU 시간 소모**: 상태 저장 및 복원에 시간이 소요된다.
    - **캐시 오염**: 캐시 메모리의 내용이 무효화될 수 있다.
    - **TLB(Translation Lookaside Buffer) 플러시**: 주소 변환 정보 갱신이 필요하다.


6. **문맥 교환 최소화 방법**:
    - **스레드 사용**: 같은 프로세스 내 스레드 간 전환은 더 가볍다.
    - **적절한 시간 할당량 설정**: 너무 짧으면 문맥 교환이 빈번해진다.
    - **프로세스 우선순위 조정**: 불필요한 문맥 교환 최소화


7. **문맥 교환 vs 모드 전환**:
    - **문맥 교환**: 프로세스 간 전환으로 오버헤드가 크다.
    - **모드 전환**: 같은 프로세스 내에서 사용자 모드와 커널 모드 간 전환으로 상대적으로 오버헤드가 작다.


📌 **요약**: 문맥 교환은 한 프로세스에서 다른 프로세스로 CPU 제어권을 넘기는 과정이다. 현재 프로세스의 상태를 저장하고 다음 프로세스의 상태를 복원한다. 멀티태스킹을 가능하게 하지만 오버헤드가 발생하므로 최적화가 중요하다. 인터럽트, 시간 할당량 만료, I/O 요청 등의 상황에서 발생하며, 효율적인 관리가 시스템 성능에 큰 영향을 미친다.



```tsx
import React from 'react';

const ContextSwitchTimeline = () => (
  <div className="flex flex-col space-y-4">
    <div className="flex items-center space-x-2">
      <div className="w-32 h-8 bg-blue-500 text-white flex items-center justify-center">프로세스 A 실행</div>
      <div className="w-24 h-8 bg-red-500 text-white flex items-center justify-center text-sm">상태 저장</div>
      <div className="w-32 h-8 bg-yellow-500 text-white flex items-center justify-center text-sm">캐시/TLB 갱신</div>
      <div className="w-24 h-8 bg-green-500 text-white flex items-center justify-center text-sm">상태 복원</div>
      <div className="w-32 h-8 bg-purple-500 text-white flex items-center justify-center">프로세스 B 실행</div>
    </div>
    <div className="flex items-center space-x-2">
      <div className="w-32 h-4"></div>
      <div className="w-80 h-4 bg-gray-300 flex items-center justify-center text-xs">문맥 교환 오버헤드</div>
    </div>
  </div>
);

export default ContextSwitchTimeline;

```

이 다이어그램은 문맥 교환의 과정과 그로 인한 오버헤드를 타임라인 형식으로 보여줍니다. 프로세스 A의 실행이 중단되고, 그 상태가 저장됩니다. 그 다음 캐시와 TLB가 갱신되고, 프로세스 B의 상태가 복원됩니다. 마지막으로 프로세스 B가 실행됩니다. 상태 저장부터 상태 복원까지의 과정이 문맥 교환 오버헤드를 나타냅니다. 이 시각자료를 통해 문맥 교환의 과정과 그로 인한 시스템 부하를 더 명확히 설명할 수 있습니다.