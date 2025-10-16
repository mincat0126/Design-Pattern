# OOP-Creational
## Factory Method
**Factory Method**: 객체 생성을 공장(Factory) 클래스로 캡슐화 처리하여 대신 생성하게 하는 생성 디자인 패턴  

**<구조>**  
**Product**: 생성될 객체의 공통 인터페이스  
**Concrete Product**: 실제로 생성되는 객체  
**Creator**: 객체를 생성하는 팩토리 메소드를 정의  
**Concrete Creator**: 실제 객체 생성 로직을 구현  

**<장점>**
1. **유연성 증가**: 새로운 제품 클래스를 쉽게 추가 가능
2. **결합도 감소**: 클라이언트 코드가 구체 클래스에 의존하지 않음
3. **확장성 증가**: 기존 코드를 수정하지 않고 기능 확장 가능

**<단점>**
1. **클래스 수 증가**: 제품 종류가 많아질수록 서브클래스도 많아질 수 있음

**<활용 예시>**    
**UI 라이브러리**: 버튼, 창 등 OS별 위젯 생성  
**게임 개발**: 캐릭터/무기/몬스터 생성 시 팩토리 메소드로 분기 처리  
**데이터베이스 연결**: DB 타입(MySQL, Oracle 등)에 따라 커넥션 객체 생성  
**프레임워크 내부 구조**: Spring의 BeanFactory, LoggerFactory 등 객체 생성을 위임하는 구조  

<img width="500" height="240" alt="image" src="https://github.com/user-attachments/assets/1c548228-0e03-4986-a362-307d4b60520c" />  
<img width="1478" height="697" alt="image" src="https://github.com/user-attachments/assets/0c31d7cb-098a-44b3-bcd8-0af8e7197721" />   
<img width="750" height="521" alt="image" src="https://github.com/user-attachments/assets/d7d2a305-5572-46c7-a3bf-df105e158eef" />  
<br><br><br><br><br>

## Abstract Factory
**Abstract Factory**: 연관성 있는 객체 군 여러개를 묶어 추상화하고, 구체적인 상황이 주어지면 팩토리 객체에서 집합으로 묶은 객체 군을 구현화 하는 패턴

**<구조>**    
**Abstract factory**: 관련 객체들을 생성하기 위한 인터페이스  
**Concrete Factory**: 실제 객체 생성 로직을 구현  
**Abstract Product**: 생성될 제품의 공통 인터페이스  
**Concrete Product**: 실제 제품 구현체  

**<장점>**
1. **객체 간 일관성 보장**: 같은 "제품군"이 항상 함께 사용됨  
2. **결합도 감소**: 클라이언트 코드가 구체 클래스에 의존하지 않음
3. **확장성 증가**: 기존 코드를 수정하지 않고 기능 확장 가능

**<단점>**
1. **클래스 수 증가**: 제품 종류가 많아질수록 서브클래스도 많아질 수 있음

**<활용 예시>**    
**GUI 프레임워크**: OS별 위젯 세트 (Windows, macOS, Linux용 UI 세트 생성)  
**게임 개발**: 테마별 객체 묶음 (예: 불속성 몬스터 + 불속성 무기)  
**데이터베이스 시스템**: DB 종류별 객체 세트 (MySQLFactory, OracleFactory 등)  
**크로스 플랫폼 앱**: 플랫폼별 리소스, 컴포넌트 생성  

<img width="700" height="240" alt="image" src="https://github.com/user-attachments/assets/ef6fc6f1-3beb-43cd-81d7-2609c702c1bf" />
<img width="700" height="240" alt="image" src="https://github.com/user-attachments/assets/64415b2d-f173-4999-b762-b457b40a12c6" />
<img width="1478" height="1121" alt="image" src="https://github.com/user-attachments/assets/d18c9398-3a5b-4c26-8708-b75916a015ba" /> 
<img width="961" height="887" alt="image" src="https://github.com/user-attachments/assets/7bad63c6-c3e0-4811-a18d-de97c5a62623" />  
<br><br>

## Factory Method + Absract Factory
<img width="1478" height="1121" alt="image" src="https://github.com/user-attachments/assets/127ca93e-0884-42cf-9b3b-eb7b2df1cc82" />  
<img width="961" height="887" alt="image" src="https://github.com/user-attachments/assets/7c6053f8-df66-4f84-8bfb-35f2ff2bad92" /> 
<br><br><br><br><br>

## Builder
**Builder**: 복잡한 객체의 생성 과정과 표현 방법을 분리하여 다양한 구성의 인스턴스를 만드는 패턴  

**<구조>**    
**Builder**: 객체를 만드는 단계(메서드)를 정의    
**ConcreteBuilder**: 실제 객체 생성 로직을 구현    
**Director**: 빌더를 이용해 생성 과정을 지휘함    
**Product**: 완성된 객체    

**<장점>**
1. **간단해진 코딩**: 복잡한 객체 생성 과정을 캡슐화  
2. **다양성 증가**: 동일한 생성 절차로 다양한 형태의 객체 생성 가능
3. **가독성 향상**: 체이닝 방식으로 명확한 단계 표현

**<단점>**
1. **간단한 코드에는 불합리**: 객체가 단순할 경우 오히려 코드가 장황해짐

**<활용 예시>**    
**Java**: StringBuilder, StringBuffer, Lombok @Builder  
**Flutter/Dart**: 테마별 객체 묶음 (예: 불속성 몬스터 + 불속성 무기)    
**게임 개발**: 캐릭터나 맵 구성 시 단계별 생성  
**웹 백엔드**: HTTP 요청 객체(Request.Builder), JSON 생성 시  

<img width="700" height="240" alt="image" src="https://github.com/user-attachments/assets/321bf8a4-699b-498e-9ee1-911bbf1efdfa" />
<img width="700" height="240" alt="image" src="https://github.com/user-attachments/assets/971630c4-4a73-4e0c-b08e-73e6eea94007" />
<img width="1312" height="875" alt="image" src="https://github.com/user-attachments/assets/a7c565e7-a057-4576-91be-3434325be6a9" />
<br><br><br><br><br>

## Singleton
**Singleton**:  단 하나의 유일한 객체를 만들기 위한 코드 패턴

**<구조>**    
**Singleton**: 자기 자신을 단 하나만 생성하고, 그 인스턴스를 외부에서 접근 가능하게 함  
**Private 생성자**: 외부에서 new로 객체를 만들지 못하도록 막음   
**Static 인스턴스**: 클래스 내부에 유일한 인스턴스를 저장  
**getInstance() 메소드**: 인스턴스에 접근할 수 있는 전역적인 진입점 제공     

**<장점>**
1. **자원 절약**: 한 번만 생성하므로 메모리 낭비 방지
2. **일관된 상태 유지**: 전역적으로 하나의 상태 유지
3. **어디서든 접근 가능**: 전역 인스턴스

**<단점>**
1. **멀티스레드 환경에서 동기화 필요**: 동시 접근 시 문제 발생 가능
2. **의존성 주입 어렵고, 결합도 높아짐**

**<활용 예시>**    
**로깅 시스템**: Logger 클래스 (로그 파일 하나로 관리)  
**설정 관리**: AppConfig, GameSettings 등  
**데이터베이스 연결**: DBConnection, ConnectionPool 등  
**캐시 시스템**: 전역 캐시 관리 객체   
**Flutter/Dart**: ServiceLocator, Provider 내부 싱글톤 관리 구조  

<img width="263" height="192" alt="image" src="https://github.com/user-attachments/assets/86beef53-98e4-427f-be95-806177f9f526" />
<img width="750" height="521" alt="image" src="https://github.com/user-attachments/assets/50627ec8-6334-4a48-89aa-837444c36b07" />  
<img width="910" height="710" alt="image" src="https://github.com/user-attachments/assets/edc77f1d-52dc-4f0b-92a6-5416e23f24d9" />
<br><br><br><br><br>

## Prototype
**Prototype**:  원본 인스턴스로 생성할 객체의 유형을 결정하고, 원본을 복제하여 새 객체를 만드는 패턴

**<구조>**    
**Prototype**: 자기 자신을 복제할 수 있는 clone() 메서드 정의  
**ConcretePrototype**: 실제 복제 로직을 구현  

**<장점>**
1. **자원 절약**: 복잡한 객체 생성 비용 절감
2. **쉬운 객체 생성**: 런타임 시 새로운 객체를 쉽게 생성 가능
3. **서브클래스 수 감소**: 상속 대신 복제를 활용 가능

**<단점>**
1. **순환 참조가 있을 경우 구현 난이도 증가**

**<활용 예시>**    
**게임 개발**: 몬스터, 총알, 맵 오브젝트 등 빠른 복제 생성  
**문서 편집기**: 복사-붙여넣기 기능   
**UI 개발**: 버튼이나 카드 컴포넌트 템플릿 복제  
**데이터 처리**: 데이터 객체를 원형으로 복제 후 변형  
**Spring Framework**: Bean Scope 중 “Prototype” 스코프 

<img width="650" height="240" alt="image" src="https://github.com/user-attachments/assets/e23eefba-dfb9-4c13-9b7a-801774d3077d" />
<img width="650" height="240" alt="image" src="https://github.com/user-attachments/assets/e5ff7ee3-4f0a-425c-af1b-9dfd38fbe43e" />
<img width="910" height="710" alt="image" src="https://github.com/user-attachments/assets/b256a275-1564-46ea-8d78-afc0082b411d" />
<br><br>

## Builder + Singleton + Prototype
<img width="1422" height="865" alt="image" src="https://github.com/user-attachments/assets/5ac23681-2dbb-4396-8c0c-8bb380659289" />
