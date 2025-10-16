# OOP-Behavioral
## Strategy
**Strategy**: 실행(런타임) 중에 알고리즘 전략을 선택하여 객체 동작을 실시간으로 바뀌도록 할 수 있게 하는 디자인 패턴

**<구조>**  
**Strategy**: 공통 알고리즘 인터페이스 정의    
**Concrete Strategy**: 실제 알고리즘 구현   
**Context**: Strategy 객체를 사용하며, 클라이언트와 전략 연결     

**<장점>**
1. **알고리즘 교체 용이**
2. **클래스 폭발 방지**: 상속 대신 전략 객체 사용
3. **유지보수 용이**:각 전략이 독립적

**<단점>**
1. **간단한 경우엔 오히려 복잡도 증가**
2. **클라이언트가 전략 객체를 관리해야 함**

**<활용 예시>**    
**게임 개발**: 캐릭터 이동, 공격 방식, AI 행동 패턴  
**정렬 알고리즘**: QuickSort, MergeSort, BubbleSort 전략 선택  
**결제 시스템**:신용카드, PayPal, 계좌이체 전략 선택  
**데이터 압축**: ZIP, RAR, TAR 알고리즘 선택  
**UI 이벤트 처리**: 클릭, 드래그, 스와이프 이벤트 전략 분리  

<img width="650" height="240" alt="image" src="https://github.com/user-attachments/assets/1731f81e-d763-4ae8-9f30-1907ec1c7995" />
<img width="650" height="240" alt="image" src="https://github.com/user-attachments/assets/1d79bdfe-9175-421d-a790-6a61c3092095" />
<img width="1020" height="765" alt="image" src="https://github.com/user-attachments/assets/a589c94d-76ab-4554-a1c4-b33f4ebc5ad1" />
<br><br><br><br><br>

## State
**State**: 객체가 특정 상태에 따라 행위를 달리하는 상황에서, 상태를 조건문으로 검사해서 행위를 달리하는 것이 아닌, 상태를 객체화 하여 상태가 행동을 할 수 있도록 위임하는 패턴

**<구조>**  
**State**: 상태별 동작을 정의  
**Concrete State**: 실제 상태와 행동 구현  
**Context**: 현재 상태 객체를 유지하며, 상태 전환 및 동작 위임  

**<장점>**
1. **복잡한 조건문 제거**
2. **유지보수 용이**: 상태별 행동 독립적
3. **상태 확장 용이**

**<단점>**
1. **상태 전환 로직이 분산될 수 있음**

**<활용 예시>**    
**게임 개발**: 캐릭터 상태 (Idle, Running, Jumping, Attacking)  
**UI 버튼**: 버튼 상태 (Enabled, Disabled, Hovered, Pressed)  
**통신 / 네트워크**: 연결 상태 (Connected, Disconnected, Reconnecting)  
**오디오/비디오 플레이어**: 재생, 일시정지, 정지 상태  
**금융 시스템**: 계좌 상태 (Active, Frozen, Closed) 

<img width="400" height="148" alt="image" src="https://github.com/user-attachments/assets/0a4a3b31-a4bb-4a1c-b135-9f344b3ba4b0" />
<img width="1215" height="766" alt="image" src="https://github.com/user-attachments/assets/afcb8370-8931-4e0c-904f-5df520a5eca0" />  
<br><br><br><br><br>

## State
**Templete Method**: 여러 클래스에서 공통으로 사용하는 메서드를 템플릿화 하여 상위 클래스에서 정의하고, 하위 클래스마다 세부 동작 사항을 다르게 구현하는 패턴

**<구조>**  
**Abstract Class**: 알고리즘의 템플릿 메서드 정의, 공통 단계 구현, 일부 추상 메서드 선언    
**Concrete Class**: 추상 메서드를 구현하여 알고리즘 세부 단계 정의  
**Template Method**: 알고리즘의 전체 구조, 실행 순서 정의     

**<장점>**
1. **코드 재사용성 증가**
2. **알고리즘 구조 일관성 유지**: 상태별 행동 독립적
3. **변경/확장 용이**

**<단점>**
1. **하위 클래스 수 증가**
2. **상위 클래스에 변경이 생기면 하위 클래스 영향 가능**

**<활용 예시>**    
**커피/차 제조 과정**: 공통 레시피 + 하위 클래스별 첨가물 추가

<img width="360" height="240" alt="image" src="https://github.com/user-attachments/assets/f3568f1f-4bf2-4450-a674-cfa10edef9a3" />
<img width="1215" height="766" alt="image" src="https://github.com/user-attachments/assets/7eb3b8ad-d892-4db8-b8f7-8b843b27bca2" />
<br><br>

## Strategy + State + Templete Method
<img width="1697" height="1142" alt="image" src="https://github.com/user-attachments/assets/294e1fae-2220-4dd3-8e8b-c30acc2789ab" />
<br><br><br><br><br>

## Command
**Command**: 요청을 객체의 형태로 캡슐화하여 사용자가 보낸 요청을 나중에 이용할 수 있도록 매서드 이름, 매개변수 등 요청에 필요한 정보를 저장 또는 로깅, 취소할 수 있게 하는 패턴

**<구조>**  
**Command**: 실행 메서드 execute() 정의  
**Concrete Command**: 실제 요청을 수행, Receiver 호출  
**Receiver**: 실제 작업을 수행하는 객체 
**Invoker**: 커맨드를 호출하여 실행   

**<장점>**
1. **유연성 증가**: 요청/수행 분리
2. **Undo/Redo 구현 용이**
3. **큐잉, 로깅, 트랜잭션 처리 가능**

**<단점>**
1. **간단한 경우엔 오히려 복잡**
2. **설계가 직관적이지 않을 수 있음**

**<활용 예시>**    
**리모컨 / GUI 버튼**: 클릭, 실행, 취소 버튼 처리  
**Undo / Redo 시스템**: 워드 프로세서, 그래픽 편집기  
**트랜잭션 처리**: DB 트랜잭션 큐잉, 롤백 가능  
**스케줄링**: 작업 예약, 큐잉   
**게임 개발**: 플레이어 행동 기록, 반복 실행, 매크로 구현  

<img width="660" height="240" alt="image" src="https://github.com/user-attachments/assets/159d3e30-c84b-4558-b673-0685601871e6" />
<img width="660" height="240" alt="image" src="https://github.com/user-attachments/assets/e31d0f13-6253-42dd-a4ce-17a554fa6dd9" />
<img width="1280" height="845" alt="image" src="https://github.com/user-attachments/assets/7483afa5-aa64-4755-8c40-a94bb514b2e2" />
<br><br><br><br><br>


## Chain of Responsibility
**Chain of Responsibility**: 클라이어트의 요청에 대한 세세한 처리를 하나의 객체가 몽땅 하는 것이 아닌, 여러개의 처리 객체들로 나누고, 이들을 사슬(chain) 처럼 연결해 집합 안에서 연쇄적으로 처리하는 패턴

**<구조>**  
**Handler**: 요청 처리 메서드와 다음 핸들러 참조  
**Concrete Handler**: 요청을 처리하거나 다음 핸들러로 전달  

**<장점>**
1. **클라이언트와 처리자 분리**
2. **처리자 추가/변경 용이**
3. **체인 길이 및 순서 유연**

**<단점>**
1. **체인 길이가 길면 성능 저하 가능**
2. **요청 처리 실패 시 어디서 실패했는지 추적 어려움**

**<활용 예시>**    
**고객 지원 / 헬프데스크**: 1차 → 2차 → 관리자 처리   
**이벤트 처리**: GUI 이벤트 전파, 이벤트 버블링  
**로그 시스템**: 여러 로거(Log)를 체인으로 연결  
**보안 / 인증**: 요청 → 인증 → 권한 검사 → 실행  
**데이터 처리 파이프라인**: 여러 처리 단계 순차 처리  

<img width="700" height="240" alt="image" src="https://github.com/user-attachments/assets/78210dda-b70b-46cf-89e3-1fa31b64ae49" />
<img width="700" height="240" alt="image" src="https://github.com/user-attachments/assets/3afe00cb-df30-4dd1-b897-c957ce57080b" />
<img width="1280" height="845" alt="image" src="https://github.com/user-attachments/assets/3ab01b4f-c620-4fac-92a3-67ca3b626365" />
<br><br><br><br><br>

## Observer
**Observer**: 옵저버(관찰자)들이 관찰하고 있는 대상자의 상태가 변화가 있을 때마다 대상자는 직접 목록의 각 관찰자들에게 통지하고, 관찰자들은 알림을 받아 조치를 취하는 패턴

**<구조>**  
**Subject**: 상태 유지, 옵저버 등록/해제, 상태 변경 시 통보  
**Observer**: Subject 상태 변경 시 업데이트 받는 인터페이스  
**Concrete Subject**: 실제 상태 저장, 상태 변경 시 알림  
**Concrete Observer**: Subject 상태에 따라 동작 수행  

**<장점>**
1. **자동 갱신으로 일관성 유지**
2. **객체 간 결합도 낮음**
3. **동적 구독/해제 가능**
4. **확장 용이**: 새 옵저버 추가 가능

**<단점>**
1. **옵저버 많으면 성능 저하 가능**
2. **갱신 순서 예측 어려움**
3. **무한 루프 가능성**

**<활용 예시>**    
**GUI 이벤트 처리**: 버튼 클릭, 텍스트 변경 이벤트  
**뉴스/알림 시스템**: 구독자에게 자동 알림  
**MVC 패턴**: Model 상태 변경 → View 갱신  
**주식/금융 데이터**: 가격 변동 → 자동 알림/차트 갱신  
**IoT / 센서 네트워크**: 센서 데이터 변화 → 여러 장치 업데이트  

<img width="600" height="240" alt="image" src="https://github.com/user-attachments/assets/06bf2eab-4385-4946-bf0a-90449368fe87" />
<img width="600" height="240" alt="image" src="https://github.com/user-attachments/assets/65dc9a55-cd88-4906-adc0-fe38fcefd2f6" />
<img width="1280" height="845" alt="image" src="https://github.com/user-attachments/assets/b1bba38e-bdf1-4d2b-ad75-8e9f63d6bcb7" />
<br><br><br><br><br>

## Memento
**Memento**: 객체의 상태 정보를 가지는 클래스를 따로 생성하여, 객체의 상태를 저장하거나 이전 상태로 복원할 수 있게 해주는 패턴

**<구조>**  
**Originator**: 상태를 생성, 저장, 복원  
**Memento**: 원본 객체의 상태를 저장 (캡슐화)  
**Caretaker**: 메멘토를 보관하고 필요 시 원본 객체에 전달  

**<장점>**
1. **객체 상태 복원 가능**: Undo / Redo
2. **캡슐화 보장**: 외부에서 내부 상태 접근 불가
3. **이력 관리 용이**

**<단점>**
1. **메모리 사용 증가능**: 상태를 저장해야 하므로
2. **상태 관리 복잡**
3. **상태 크기가 크면 성능 문제 발생 가능**

**<활용 예시>**    
**문서 편집기**: Undo / Redo 기능 (Word, Excel)  
**게임**: 체크포인트, 세이브/로드 기능   
**그래픽 편집기**: 이미지 편집 상태 되돌리기  
**데이터베이스 트랜잭션**: 이전 상태로 롤백  
**IDE**: 코드 편집 Undo 기능  

<img width="680" height="240" alt="image" src="https://github.com/user-attachments/assets/a9da58d7-851b-412a-9f98-3625b7d8aae5" />
<img width="680" height="240" alt="image" src="https://github.com/user-attachments/assets/c0f70b33-4854-4836-90c8-0562072f16d9" />
<img width="1280" height="845" alt="image" src="https://github.com/user-attachments/assets/8167e2cc-667f-406d-9348-13edd23197f4" />
<br><br><br><br><br>

## Mediator
**Mediator**: 객체의 상태 정보를 가지는 클래스를 따로 생성하여, 객체의 상태를 저장하거나 이전 상태로 복원할 수 있게 해주는 패턴

**<구조>**  
**Mediator**: 동료 객체 간 통신을 정의  
**Concrete Mediator**: 통신 로직 구현, 객체 관리  
**Colleague**: Mediator를 통해 메시지 전달  
**Concrete Colleague**: 실제 동작 구현, Mediator 호출  

**<장점>**
1. **객체 간 결합도 낮음**
2. **통신 로직 집중화로 유지보수 용이**
3. **확장성과 유연성 증가**

**<단점>**
1. **Mediator가 커지면 복잡**
2. **단일 책임 원칙 위반 가능**

**<활용 예시>**    
**GUI 프레임워크**: 윈도우, 버튼, 텍스트박스 간 이벤트 중재  
**항공 관제 시스템**: 비행기 ↔ 관제 센터  
**채팅 시스템 / 메시징**: 사용자 간 메시지 전달 중앙화  
**게임 개발**: 캐릭터, 오브젝트 간 이벤트 중재  
**IoT 시스템**: 센서와 장치 간 메시지 관리  

<img width="600" height="240" alt="image" src="https://github.com/user-attachments/assets/8d78c3f6-85e7-4f38-ae90-1b9765e5d9b5" />
<img width="600" height="240" alt="image" src="https://github.com/user-attachments/assets/afc49bec-f56b-4fa7-884d-166f30355692" />
<img width="1280" height="845" alt="image" src="https://github.com/user-attachments/assets/3818a747-3f5d-4a0b-9b46-bf12353395e0" />

## Mediator
**Visitor**: 객체의 구조와 그 구조에서 수행되는 작업을 분리하여 구현하는 패턴

**<구조>**  
**Visitor**: 객체 구조(Element)에 수행할 연산 정의  
**Concrete Visitorr**: 실제 연산 구현  
**Element**: Visitor를 받아들이는 accept() 메서드 정의  
**Concrete Element**: Visitor의 visit() 호출  
**ObjectStructure**: Element 집합 관리, Visitor 적용  

**<장점>**
1. **새로운 기능 추가 용이**
2. **객체 구조 변경 없이 연산 확장 가능**
3. **여러 타입의 객체 일괄 처리 가능**

**<단점>**
1. **Element가 많으면 Visitor 코드 복잡**
2. **설계가 직관적이지 않을 수 있음**
3. **객체 구조가 자주 변경되면 부적합**

**<활용 예시>**    
**회계/재무 시스템**: 다양한 계산(세금, 할인, 배송비) 처리  
**컴파일러**: AST(Abstract Syntax Tree) 순회하며 연산 수행  
**문서 처리**: 문서 요소별 변환, 렌더링, 통계 계산  
**그래픽/게임 개발**: 오브젝트 순회하며 렌더링, 충돌 체크  
**데이터 분석**: 서로 다른 데이터 타입에 대한 연산 적용  

<img width="750" height="240" alt="image" src="https://github.com/user-attachments/assets/39e9d0f1-a57e-4759-90e0-ed7c33c9e5a8" />
<img width="750" height="240" alt="image" src="https://github.com/user-attachments/assets/a0ca7536-d3e2-4217-941d-f3c58253bfc7" />
<img width="1280" height="845" alt="image" src="https://github.com/user-attachments/assets/63d9f476-49a2-44a2-bf6d-6d290c44acd7" />

## Iterator
**Iterator**: 일련의 데이터 집합에 대하여 순차적인 접근(순회)을 지원하는 패턴

**<구조>**  
**Iterator**: 순회 기능 정의 (hasNext(), next())  
**Concrete Iterator**: 컬렉션 순회 구현, 현재 위치 유지  
**Aggregate**: 반복자를 반환하는 인터페이스  
**Concrete Aggregate**: 실제 데이터 집합 구현, Iterator 생성  

**<장점>**
1. **내부 구조 변경에도 클라이언트 코드 영향 최소**
2. **여러 컬렉션에 동일한 순회 방식 적용 가능**
3. **읽기 편하고 직관적인 반복 처리**

**<단점>**
1. **단순한 경우 오히려 코드가 복잡**
2. **실시간 변경 시 일관성 문제 가능**

**<활용 예시>**    
**컬렉션 라이브러리**: List, Set, Map 순회 
**파일 시스템**: 디렉토리 파일 순회

<img width="590" height="240" alt="image" src="https://github.com/user-attachments/assets/1f96065b-99a0-4661-81a7-7c78ad27e7a1" />
<img width="590" height="240" alt="image" src="https://github.com/user-attachments/assets/34948d56-7973-4e8a-88de-3d6a15daea65" />
<img width="1280" height="845" alt="image" src="https://github.com/user-attachments/assets/ef0761c7-65d7-457f-bbd1-dc2ce760e5b0" />

