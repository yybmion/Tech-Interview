# 프로그램(Program)에 대해서 설명해주세요.

1. **프로그램의 정의**:
    - 특정 작업을 수행하기 위한 **명령어들의 집합**이다.
    - 컴퓨터가 실행할 수 있는 형태로 저장된 `instructions`의 `sequence`이다.


2. **프로그램의 구성 요소**:
    - **실행 코드 (Executable code)**
    - **데이터 (Data)**
    - **리소스 (Resources: 아이콘, 이미지 등)**


3. **프로그램과 프로세스의 관계**:
    - 프로그램은 디스크에 저장된 **정적인 entity**이다.
    - 프로세스는 **실행 중인 프로그램의** `인스턴스`이다.
    - 하나의 프로그램은 **여러 프로세스를 생성**할 수 있다.


4. 프로그램의 생명주기:
    - **작성 (Writing)**
    - **컴파일 (Compiling)**
    - **링킹 (Linking)**
    - **로딩 (Loading)**
    - **실행 (Execution)**


5. **프로그램의 유형**:
    - **시스템 프로그램**: **운영체제의 일부로 동작**하는 프로그램
    - **응용 프로그램**: **사용자가 특정 작업을 수행**하기 위해 사용하는 프로그램


6. **운영체제의 역할**:
    - 프로그램 실행을 위한 환경 제공
    - 메모리 할당 및 관리
    - 프로세스 스케줄링
    - 입출력 작업 관리


7. **프로그램 실행 과정**:
    - 운영체제가 프로그램을 **메모리에 로드**
    - `프로그램 카운터(PC)`를 **프로그램의 시작 주소로** 설정
    - CPU가 **명령어를 하나씩 실행**


📌 **요약**: 프로그램은 특정 작업을 수행하기 위한 **명령어 집합**으로, **실행 코드와 데이터로 구성**된다. 운영체제는 프로그램 실행 환경을 제공하고, **프로그램이 실행되면 프로세스**가 된다. 프로그램은 `작성`, `컴파일`, `링킹`, `로딩`, `실행`의 생명주기를 거치며, 운영체제는 이 과정을 관리한다.

___
### 보충정리

```mermaid
graph LR
    A[작성] --> B[컴파일]
    B --> C[링킹]
    C --> D[로딩]
    D --> E[실행]
    E -->|프로그램 종료| F[종료]
    E -->|다시 실행| D

```

이 다이어그램은 프로그램의 기본적인 `생명주기`를 보여줍니다. 프로그램이 작성되고 컴파일된 후, 필요한 라이브러리와 링크되어 실행 가능한 형태가 됩니다. 그 다음 메모리에 로드되어 실행됩니다. 프로그램이 종료되면 생명주기가 끝나지만, 다시 실행될 수 있음을 화살표로 표시했습니다. 이 시각자료를 통해 프로그램의 생명주기를 더 명확히 설명할 수 있습니다.


### 프로그램 실행

모든 프로그램은 운영체제가 실행되기 위한 **메모리 공간을 할당해 줘야 실행**될 수 있다. 운영체제가 메모리 공간을 할당해주면 프로세스가 필요로 하는 `재료`들이 메모리에 올라간다.
그것은 바로 `code,data,heap,stack`이다.

간단히 말하자면
`code` : 실행 명령을 포함하는 코드들
`data` : Static 변수 혹은 Global 변수
`heap` : 동적 메모리 영역
`stack` : 지역변수, 매개변수, 반환 값 등 일시적인 데이터

추가로 프로세스에 대한 정보를 담고 있는 **PCB블럭**이 프로세스 생성 시 함께 만들어진다.

### PCB란

- 운영체제가 프로세스를 제어하기 위해 정보를 저장해 놓는 곳으로, 프로세스의 `상태 정보`를 저장하는 구조체다.
- 프로세스의 상태 관리와 **문맥 교환(Context Switching)을** 위해서 필요하다.

**PCB**에는 간단히 얘기하자면 `프로세스의 고유 ID`, `프로레스의 상태`(Create, Ready, Running 등등), `PC`(프로세스를 위해 실행될 다음 명령어의 주소) 등의 정보가 들어있다.