# OOP-Structual
## Adapter
**Adapter**: 호환성이 없는 인터페이스 때문에 함께 동작할 수 없는 클래스들을 함께 작동해주도록 변환 역할을 해주는 패턴

**<구조>**    
**Target**: 클라이언트가 기대하는 인터페이스
**Adaptee**: 이미 존재하지만 인터페이스가 맞지 않는 클래스
**Adapter**: Adaptee를 Target 인터페이스에 맞게 변환

**<장점>**
1. **호환성 향상**: 인터페이스가 다른 객체를 쉽게 연결 가능
2. **재사용성 증가**: 기존 클래스 재활용 가능
3. **유연성 확보**: 시스템 수정 없이 통합 가능

**<단점>**
1. **성능 저하 가능성**: 변환 과정이 추가됨
2. **남용 시 가독성 저하**: 코드 흐름이 어댑터를 통해 우회

**<활용 예시>**    
**Java I/O**: InputStreamReader, OutputStreamWriter (byte ↔ char 변환)  
**GUI 라이브러리**: 서로 다른 이벤트 리스너 형식 연결  
**API 연동**: 서로 다른 외부 API 포맷을 맞출 때  
**게임 개발**: 오래된 엔진 코드와 새로운 시스템을 연결  
**데이터 처리**: JSON ↔ XML 포맷 변환, DB ↔ Object 변환 

<img width="640" height="240" alt="image" src="https://github.com/user-attachments/assets/b551f624-91e0-4622-bdce-16c4017bf65f" />
<img width="640" height="240" alt="image" src="https://github.com/user-attachments/assets/d622ef56-0f0e-4361-a13e-bb3b07ed2de2" />
<img width="891" height="702" alt="image" src="https://github.com/user-attachments/assets/9a4ef6d5-b1f0-45fd-8787-a97aaff03db2" />
<br><br><br><br><br>

## Proxy
**Proxy**: 대상 원본 객체를 대리하여 대신 처리하게 함으로써 로직의 흐름을 제어하는 패턴

**<구조>**    
**Subject**: 실제 객체와 프록시가 모두 구현해야 할 인터페이스  
**RealSubject**: 원래 수행할 핵심 로직을 가진 클래스  
**Proxy**: RealSubject에 접근을 제어하고, 필요 시 RealSubject를 호출  

**<종류>**
**Virtual Proxy (가상 프록시)**: 무거운 객체를 실제로 필요할 때만 생성 (지연 초기화)  
**Remote Proxy (원격 프록시)**: 원격 서버의 객체를 로컬에서 대리 (RPC, gRPC 등)  
**Protection Proxy (보호 프록시)**: 접근 권한 제어  
**Caching Proxy (캐싱 프록시)**: 동일한 요청에 대해 결과를 저장/재사용  
**Logging / Monitoring Proxy**: 호출 이력을 남기거나, 성능 측정  

**<장점>**
1. **접근 제어 가능**: 보안, 권한 관리
2. **성능 최적화**: 지연 로딩, 캐싱
3. **로깅 및 트래킹**: 모니터링 용도
4. **객체 생명주기 관리 용이**

**<단점>**
1. **코드 복잡성 증가**: 변환 과정이 추가됨  
2. **디버깅 어려움**: 중간 계층이 많아짐

**<활용 예시>**    
**Spring Framework**: AOP(Aspect-Oriented Programming)에서 프록시 사용 (ex. 트랜잭션 관리, 로깅)  
**데이터베이스**: Lazy Loading (JPA 엔티티 프록시)  
**보안 시스템**: 사용자 접근 제한  
**네트워크**: 원격 호출 프록시 (RPC, gRPC)  
**캐싱 시스템**: 동일 요청에 대한 결과 재사용  

<img width="620" height="240" alt="image" src="https://github.com/user-attachments/assets/83ccf6aa-2b04-4bfa-9ac0-a472b97612cf" />
<img width="620" height="240" alt="image" src="https://github.com/user-attachments/assets/b5f414f7-beab-4b0c-ba96-912b9c5e3bee" />
<img width="891" height="702" alt="image" src="https://github.com/user-attachments/assets/48b6f888-c328-4383-8dda-3af4749b42ad" />
<img width="891" height="702" alt="image" src="https://github.com/user-attachments/assets/4d5b443a-61e5-4689-9cde-f9d18228ca3f" />
<br><br><br><br><br>

## Facade
**Facade**: 사용하기 복잡한 클래스 라이브러리에 대해 사용하기 편하게 간편한 인터페이스(API)를 구성하기 위한 패턴

**<구조>**    
**Facade**: 여러 복잡한 서브시스템을 단순화하여 통합 인터페이스 제공  
**Subsystem Classes**: 실제 기능을 수행하는 여러 클래스  

**<장점>**
1. **사용성 향상**: 단순하고 직관적인 인터페이스
2. **의존성 감소**: 서브시스템과 클라이언트 분리
3. **유지보수 용이**: 내부 구조 변경 시 외부 영향 최소화

**<단점>**
1. **추가 추상화로 인한 코드 중복 가능성**
2. **퍼사드 클래스가 너무 커지면 ‘God Object’ 문제 발생 가능**

**<활용 예시>**    
**프레임워크 / 라이브러리**: Spring의 JdbcTemplate, RestTemplate (복잡한 DB/HTTP 작업을 단순화)  
**그래픽 엔진**: 렌더링, 사운드, 물리 등 여러 시스템을 하나의 인터페이스로 묶음    
**운영체제 API**: 복잡한 OS 호출을 단순한 함수로 제공  
**비즈니스 로직**: 여러 하위 서비스 호출을 하나의 서비스로 묶어 제공  

<img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/8fbe7231-fb03-42a7-bef1-2e8aca1062a0" />
<img width="350" height="300" alt="image" src="https://github.com/user-attachments/assets/acdbf77c-811f-4eb0-bd39-b64f13ae4877" />
<img width="891" height="702" alt="image" src="https://github.com/user-attachments/assets/372f47de-489c-49b3-ab56-9e806c8452fd" />
<img width="1066" height="937" alt="image" src="https://github.com/user-attachments/assets/47832714-e009-4982-a041-9701b8c58d87" />
<br><br><br><br><br>

## Decorator
**Decorator**: 대상 객체에 대한 기능 확장이나 변경이 필요할때 객체의 결합을 통해 서브클래싱 대신 쓸수 있는 유연한 대안 패턴

**<구조>**    
**Component**: 기본 기능의 공통 인터페이스
**Concrete Component**: 실제로 기능을 수행하는 객체
**Decorator**: 컴포넌트를 감싸고, 동일한 인터페이스를 구현
**Concrete Decorator**: 새로운 기능을 추가하거나 기존 기능을 확장

**<장점>**
1. **동적 확장**: 실행 중에도 객체 기능을 추가할 수 있음
2. **조합 기반 설계**: 상속 없이 기능 확장 가능
3. **유연한 구조**: 여러 데코레이터를 조합해 다양한 기능 구성 가능
4. **인터페이스 일관성 유지**: 원래 객체와 동일한 형태로 취급 가능

**<단점>**
1. **순서 의존성 존재**: 감싸는 순서에 따라 결과가 달라질 수 있음

**<활용 예시>**    
**Java I/O**: BufferedReader, InputStreamReader, FileInputStream 등 (I/O Stream 데코레이션 구조)  
**GUI 시스템**: 컴포넌트에 테두리, 스크롤바, 그림자 효과 등을 추가  
**웹 개발**: 요청/응답 필터(RequestWrapper, ResponseWrapper)  
**게임 개발**: 아이템 버프, 능력치 효과를 여러 개 중첩  
**Python / Dart**: @decorator 문법으로 함수나 클래스 기능 확장  

<img width="500" height="396" alt="image" src="https://github.com/user-attachments/assets/5e4d7c98-4d60-4f7a-b23c-86965d72e080" />
<img width="1470" height="927" alt="image" src="https://github.com/user-attachments/assets/04388f32-8959-4322-9918-1de2e7973d4c" />
<br><br><br><br><br>

## Bridge
**Bridge**: 구현부에서 추상층을 분리하여 각자 독립적으로 변형이 가능하고 확장이 가능하도록 하는 패턴

**<구조>**    
**Abstraction**: 상위 수준의 기능을 정의하고, Implementor에 대한 참조를 가짐  
**RefinedAbstraction**: Abstraction을 구체적으로 확장  
**Implementor**: 하위 수준의 구현을 위한 인터페이스  
**Concrete Implementor**: 실제 구현 클래스 (플랫폼, 장치, API 등)  

**<장점>**
1. **확장성 뛰어남**: 양쪽을 독립적으로 확장 가능
2. **코드 의존성 감소**: 한 계층 변경이 다른 쪽에 영향 적음
3. **클래스 수 감소**: 조합형 설계 가능

**<단점>**
1. **설계 초기엔 직관적이지 않음**: OOP 경험이 필요

**<활용 예시>**    
**그래픽 / 렌더링 시스템**: Shape (도형) ↔ DrawingAPI (렌더링 엔진)  
**게임 엔진**: 무기 ↔ 효과, 캐릭터 ↔ 스킨 시스템  
**UI 프레임워크**: Window ↔ OperatingSystem (Windows, Mac, Linux)  
**데이터베이스 계층**: DAO ↔ DB Driver (MySQL, PostgreSQL 등)  
**디바이스 제어**: 리모컨 ↔ 장치 (TV, 오디오 등)  

<img width="580" height="240" alt="image" src="https://github.com/user-attachments/assets/519d44c6-be83-4fda-aeb4-dbd5f9f5cfe7" />
<img width="580" height="240" alt="image" src="https://github.com/user-attachments/assets/f487b02a-6f81-4d67-85b2-488a1829fabc" />
<img width="1470" height="927" alt="image" src="https://github.com/user-attachments/assets/509e88a7-8f24-4a52-b862-0e694b242239" />
<img width="801" height="771" alt="image" src="https://github.com/user-attachments/assets/6b283ec7-88e6-4a63-80e5-cb9cc8c3bd31" />
<br><br><br><br><br>

## Flyweight
**Flyweight**: 재사용 가능한 객체 인스턴스를 공유시켜 메모리 사용량을 최소화하는 패턴 

**<구조>**    
**Flyweight**: 상위 수준의 기능을 정의하고, Implementor에 대한 참조를 가짐    
**Concrete Flyweight**: 공유 가능한 실제 객체  
**Unshared Concrete Flyweight**: 공유하지 않고 개별적으로 사용되는 객체  
**Flyweight Factory**: 객체를 생성하거나 캐싱하여 재사용 관리  

**<장점>**
1. **메모리 사용량 절감**: 중복 객체 방지
2. **객체 생성 비용 절감**
3. **공통 데이터 일관성 유지**

**<단점>**
1. **외부 상태 관리가 필요함**: 클라이언트가 일부 책임을 짐

**<활용 예시>**    
**게임 개발**: 탄환, 파티클, 나무, 돌 등 대량 오브젝트  
**문서 편집기**: 글꼴(Font) 객체 재사용  
**그래픽 시스템**: 아이콘, 스프라이트 캐시  
**데이터베이스 커넥션 풀**: 동일한 연결 객체를 재사용  
**문자 렌더링 엔진**: 문자의 “모양”만 공유, 위치는 외부에서 관리  

<img width="720" height="240" alt="image" src="https://github.com/user-attachments/assets/f3ffb182-6484-41bf-89dd-cfaeb1fd4188" />
<img width="720" height="240" alt="image" src="https://github.com/user-attachments/assets/305f663a-165a-4c2e-a745-d5bc2f1ddde5" />
<img width="801" height="771" alt="image" src="https://github.com/user-attachments/assets/d63ca492-4e85-4f3a-9a2f-56046ae64659" />
<br><br><br><br><br>

## Composite
**Composite**: 복합 객체와 단일 객체를 동일한 컴포넌트로 취급하여, 클라이언트에게 이 둘을 구분하지 않고 동일한 인터페이스를 사용하도록 하는 패턴

**<구조>**    
**Component**: 공통 인터페이스 (Leaf와 Composite 모두 이걸 상속)  
**Leaf**: 실제 동작을 수행하는 객체 (자식 없음)  
**Composite**: 여러 Component를 포함하고, 공통 인터페이스로 동일하게 행동  

**<장점>**
1. **트리 구조를 간단하게 처리 가능**
2. **복잡한 구조를 단일 인터페이스로 통일**
3. **확장 용이**: 새로운 노드 추가가 쉬움

**<단점>**
1. **타입 안정성이 낮아질 수 있음**: 공통 인터페이스 때문에 불필요한 기능 노출 가능

**<활용 예시>**    
**파일 시스템**: 폴더 안에 폴더/파일 구조  
**UI 프레임워크**: 윈도우 → 패널 → 버튼 → 텍스트 등 계층적 구조  
**그래픽 씬 그래프**: 객체들이 계층적으로 연결된 렌더 구조  
**회사 조직도**: CEO → 부서 → 직원 구조 표현  

<img width="960" height="620" alt="image" src="https://github.com/user-attachments/assets/ac013545-5db9-4c53-a1ac-3a83a8b21e2c" />
<img width="801" height="771" alt="image" src="https://github.com/user-attachments/assets/3adce571-7e48-4e7f-91f5-6a8abc258873" />
