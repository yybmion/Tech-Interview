# 동기식 I/O와 비동기식 I/O에 대해서 설명해주세요.

1. **I/O 작업의 정의**:
    - 입력/출력(I/O) 작업은 컴퓨터 시스템이 외부 장치와 데이터를 주고받는 과정이다.
    - 프로세스의 실행 흐름에 중요한 영향을 미친다.


2. **동기식 I/O**:
    - I/O 작업이 **완료될 때까지** **프로세스가 대기**한다.
    - 작업 완료 **후에야 다음 명령어를 실행**한다.
    - 구현이 간단하고 직관적이다.


3. **비동기식 I/O**:
    - I/O 작업을 요청한 후 프로세스가 **다른 작업을 계속 수행**한다.
    - I/O 완료 시 `인터럽트`나 `콜백`을 통해 알림을 받는다.
    - 시스템 자원을 효율적으로 사용할 수 있다.


4. **동기식 I/O의 특징**:
    - **순차적인 처리가 보장**된다.
    - 프로그램 흐름이 예측 가능하다.
    - I/O 작업 중 **CPU가 유휴 상태**가 될 수 있다.


5. **비동기식 I/O의 특징**:
    - 다중 I/O 작업의 **병렬 처리가 가능**하다.
    - CPU 활용도가 높다.
    - 프로그램 구조가 복잡해질 수 있다.


6. **사용 사례**:
    - **동기식 I/O**: 간단한 파일 읽기/쓰기, 데이터베이스 쿼리
    - **비동기식 I/O**: 네트워크 통신, 대용량 파일 처리, 실시간 시스템


7. **성능 비교**:
    - **동기식 I/O**: 단순 작업에서 **오버헤드가 적다**.
    - **비동기식 I/O**: 복잡하거나 장시간 I/O 작업에서 **효율적**이다.


📌 **요약**: `동기식 I/O`는 작업 완료까지 프로세스가 **대기하며 순차적 처리를 보장**한다. `비동기식 I/O`는 작업 요청 후 **다른 작업을 수행할 수 있어 효율적이지만 복잡**할 수 있다. 각각의 장단점을 고려하여 상황에 맞게 선택해야 한다.

___
### 보충정리

![img.png](동기_비동기.png)


이 다이어그램은 동기식 I/O와 비동기식 I/O의 처리 과정 차이를 시각적으로 보여줍니다. 동기식 I/O에서는 I/O 작업 동안 프로세스가 대기하는 반면, 비동기식 I/O에서는 I/O 작업이 백그라운드에서 실행되는 동안 프로세스가 계속 실행됩니다. 이 시각자료를 통해 두 방식의 차이점을 더 명확히 설명할 수 있습니다.


### Blocking/NonBlocking 그리고 Synchronize/Non-Synchroniz에 대한 정리가 잘되어있는 블로그를 소개한다.

https://velog.io/@guswns3371/%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C-Synchronous%EC%99%80-Asynchronous-Blocking%EA%B3%BC-Non-Blocking