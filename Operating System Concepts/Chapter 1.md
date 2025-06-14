# 01. 운영체제

## 운영체제란?

컴퓨터 시스템을 운영하는 소프트웨어

- HW 디바이스를 제어할 수 있는 OS가 존재하고 이를 통해 Application에서 HW를 사용한다.

아두이노나 라즈베리는 직접 HW를 제어하지만 HW가 복잡해질수록 OS를 통해 제어하는 것이 편함

### 컴퓨터란?

컴퓨터는 정보를 처리하는 기계 (a machine that processes the informations)

- 컴퓨터가 아님 (운영체제가 필요 없음)
    - 텔레비전, 자동차, 지갑 등등..
- 컴퓨터 (운영체제가 필요함)
    - 휴대폰, 스마트 tv, 자율주행 자동차, Auto sar 자동차, 스마트 월렛

### 정보란?

클로드 섀넌이 1930년대에 정리한 수학적으로 정보를 정의함

정보의 단위가 1이라면 1bit라고 부른다 (binary digit)

정보의 량을 정확히 단위로 표현 가능

정보란 → 불확실성을 측정해서 이를 수치적으로 표현한 것

컴퓨터가 정보를 처리하는 것

- 정보의 최소 단위 : bit
- 정보를 처리하기 위해서는 정보의 상태를 변환할 수 있는 물리적 장치 필요 ( 0에서1로, 1에서 0으로)
- 물리적 장치 ⇒ 부울 대수: NOT, AND, OR
- 논리 게이트를 만들면 논리 회로가 가능하다.
    - 무어의 법칙, 황의 법칙 등등
- 정보의 저장: 플립-플롭
- 정보의 전송: 데이터 버스, RF(무선)

### 컴퓨터가 정보를 처리한다는 것

- 덧셈: 반가산기, 전가산기
- 뺄셈: 2의 보수 표현법
- 곱셈, 나눗셈: 덧셈과 뺄셈의 반복
- 실수: 부동 소수점 표현법
- 함수: GOTO

→ 위 다섯개를 이용해 삼각함수, 동영상 등등

그럼 컴퓨터는 정보를 처리할 수 있으니 모든 것을 다할 수 있나?

- 범용성(universlity)
    - NOT, AND, OR 게이트(bool)만으로 모든 계산을 할 수 있음
    - 위의 세개를 섞어서 사용하는 것은 매우 어려우므로 NAND 게이트만으로 모든 계산을 할 수 있음
- 범용 컴퓨터: general-purpose computer
    - 소프트웨어가 하고자하는 모든 것을 하드웨어가 지원해준다면 컴퓨터라고 함
    - 특정한 목적으로 만들어 진것들(계산기..) 등 은 컴퓨터라고 부르지 않는다.(소프트웨어에 종속성)
- 계산가능성 (computability)
    - Turing-computable: 튜링 머신으로 계산 가능한 것
    - 정지문제(Halting Problem): 튜링 머신으로 풀 수 없는 문제
    
    컴퓨터가 모든 것을 할 수 있는 것은 아니고 튜링 머신으로 풀 수 있는 것을 할 수 있다라고 정의
    

## 컴퓨터는 누가 만들었는가?

- 컴퓨터의 할아버지: Alan Turing - Turing Machine
- 컴퓨터의 아버지: John von Neumann - ISA: Instrction Set Architecture

### 앨런 튜링

![Untitled](https://user-images.githubusercontent.com/37995685/217672969-8204704b-7f81-446b-971e-9a5a1a53c1da.png)


- 헤드와 테이프가 있으면 이를 가지고 목적을 가진 튜링 머신을 만들 수 있고 이를 똑가팅 따라하는 유니버설 튜링 머신을 가질 수 있음

![Untitled 1](https://user-images.githubusercontent.com/37995685/217672987-befa1977-6c03-4200-a789-fbfffe1f321d.png)


이게 현대적으로 넘어오면서 

- 헤드 → CPU
- 테이프 → 메모리
- 유니버설 튜링 머신 → 운영체제
- 튜링 머신 → 응용 프로그램

CPU, RAM, Application Programs, Operating System ⇒ 현대적 컴퓨터의 원형을 앨런 튜링이 설계함

### 폰 노이만

![Untitled 2](https://user-images.githubusercontent.com/37995685/217673036-01ce141a-4066-4a89-b633-ab07e81ec77f.png)

처음으로 Stored-program(내장형 프로그램)을 도입함

- 메모리(RAM)에 프로그램을 저장함
- RAM에 프로그램(명령어)를 저장해 놓으면 CPU에서 하나씩 fetch하면서 실행(excute)함

→ 이를 폰 노이만 아키텍처라고 부른다 (ISA)

### 프로그램이란?

컴퓨터 하드웨어에게 특정 task를 실행시키는 명령어들의 집합

### 운영체제도 프로그램인가요?

![Untitled 3](https://user-images.githubusercontent.com/37995685/217673051-6158d180-ebce-4bb7-8693-9c246a496a7c.png)

운영체제는 프로그램의 일종으로 컴퓨터에서 항상 실행중인 프로그램이다.

CPU위에서 가장 기본적으로 HW를 컨트롤하는 운영체제로 시스템 서비스를 애플리케이션에게 제공함 (애플리케이션 개발자는 HW를 신경 X)

- Application과 HW 사이의 인터페이스 역할

### 운영체제 역할

- Processes 관리
- resources 관리
- user interfaces 관리 (마우스, 키보드 등등)
