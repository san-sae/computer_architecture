# Computer Architecture

- 전기 : 에너지
    - 흐름 제어
    - switch ; 개폐기
- 전자 : 신호
    - 신호 제어

- 도체(Conductor)
- 부도체(Bankrupt entity)
- 반도체(Semiconductor)
- diode : 2극

***
# 컴퓨터 구조의 계층
<img width="50%" src="./image/computer.png">  
  
> ## 반도체 기술
<img width="25%" src="./image/transistor.jpg">  &larr; transistor

- 스위칭 소자 ex. `transistor`(전류 제어)  
    - 반도체의 물리적 특성을 이용하여 전기신호를 전달 or 차단하는 기능 가짐
        - 각 상태를 2진수 형태의 1 bit로 표현
        - `off` = 논리 0 / `on` = 논리 1
- `logic gate` : transistor를 조합하여 논리 값을 다루는 기본 소자(논리 연산 수행)
    - 논리 회로의 동작을 표현하는 기본 논리 소자
    - AND, OR 연산 등
        
> ## 논리회로
- `logic circuit`(논리회로) cf> building block : 미리 만들어 놓은 모듈
    - **combinational logic circuit**(조합논리회로) ex. 디코더, 인코더, 멀티플렉서, 연산기
    - **sequential logic circuit**(순차논리회로) ex. register, counter
- `논리 개념` : 참과 거짓의 개념(실제 회로에서 발생하는 전압과 전류 등 `물리 개념`에서 탈피) 
- logic gate를 조합하여 만들
    - `Boolean Algebra`(부울 대수) : 컴퓨터 동작을 **참**(1) / **거짓**(0)으로 표현

> ## 컴퓨터 구성요소
- `Programmer model` : 컴퓨터 조직 중 프로그램을 작성을 위해 제공되는 부분  
    ex. instruction set, register(수와 용도), 기억장치 (주소지정방식)
    - `instruction set`(명령어 집합) : 명령어의 모임
        - 하드웨어와 소프트웨어 연결
        - `instruction` : 컴퓨터가 해석/실행 가능한 가장 기본 작업 단위
            1. `machine instruction` : binary code로 정의
            2. `assembly language` : 기계어를 문자로 표현
                - 기계어와 일대일 대응
                - 기계 의존적(Programmer model에 의존)
                - `assembler` : 어셈블리 프로그램 $\rightarrow$ 기계어 프로그램 번역  
            3. `high-level language`
                - 컴퓨터 구조와 독립적(Programmer model와 독립적)
                - `compiler`
***
- 시스템 프로그램 : OS, compiler, 파일 탐색기 등
- 응용 프로그램 : 오피스 프로그램, 게임, 웹브라우저 등
***                
- `컴퓨터 조직` : 컴퓨터 구성요소들의 세부사항 및 서로 간의 물리적 연결
    1. `CPU`(Central Processing Unit, 중앙처리장치) : 프로그램의 지시에 따라 데이터 처리  
        1. 제어장치 : 명령어 의미 해석, 제어신호 생성  
        2. 처리장치 : 제어장치의 지시에 따라 명령어 실행(데이터 처리)  
            1. `register` : 연산에 필요한 데이터와 상태를 잠시 저장하는 기억소자  
            2. 연산장치
    2. `Memory Unit`(기억장치)
        - 프로그램과 데이터(처리할 명령어, 처리될 데이터) 저장
        - CPU와 온라인으로 연결
    3. `Input/Output Device`(입출력장치) : 프로그램과 데이터를 컴퓨터로 입력, 처리 결과를 외부로 출력
    4. `System Bus`(시스템 버스) : `data path`(데이터 전달 경로)
        - 한 개의 선은 1 bit의 정보 전달
        - address, data, 제어신호 전달

>### 컴퓨터 변천사
- 기계식 : 1600년대, 산술 계산용
- 전자식
    - 1세대 : 진공관, 에니악(1946년, 전자식 컴퓨터의 시작)
    - `stored program`(내장형 프로그램 방식) 도입
        - Von Neumann이 제안(1945년)
        - 프로그램과 데이터를 기억장치에 저장해둠
        - 중앙처리장치로 명령어를 하나씩 보내 실행
    - 2세대 : `transistor`(1954년), 자기코어(`magnetic core`) 기억장치, 고급 언어 도입
        - transistor : 진공관에 비해 발열 $\downarrow$, 동작 속도 $\uparrow$
    - 3세대 : `IC`(Integrated Circuit, 집적회로, 1960년대), 반도체 기억장치, OS(Operating System)
    - 4세대 : `VLSI`(Large Scale IC, 고밀도 집적회로), microprocessor(1970년대)
        - CPU : printed board 위 많은 전자회로 칩들을 연결
        - `microprocessor` : cpu를 한 개의 칩 안에 내장한 소자
        - `microcontroller`(MCU) : 마이크로프로세서(processor core)와 입출력 모듈을 하나의 칩으로 만듦
        ***
    - 1980년대 중반 ; 처리 용량 개선
        - processor가 한 번에 처리하는 비트 수 $\uparrow$
        - `family`(계열) : 버스 폭, 연산기 처리능력 $\uparrow$, 기억장치 $\uparrow$ $\Rightarrow$ `upward compatibility`(상위호환)
    - 1980년 중반 이후 ; 조직개선
        - `cache memory`(캐시기억장치) 도입
        - `virtual memory`(가상기억장치) 도입
        - `파이프라인 기법` : 여러 개 명령어를 동시에 처리
        - `RISC`(Reduced Instruction Set Computer)
        - `superscalar processor` : 한 번에 여러 명령어 처리 
    - 2000년대
        - 64bit processor
        - `multi-core` : 한 개의 칩 내 여러 개의 프로세서 탑재

