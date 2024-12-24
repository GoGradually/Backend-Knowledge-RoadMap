- Application Context라고도 불림


### 구성요소
![[Pasted image 20241214155801.png]]
- [[BeanFactory]]
- MessageSource
    - 국제화 기능
- ApplicationEventPublisher
    - 이벤트 발행 기능
- ResourceLoader
    - 리소스 로딩 기능
- EnviormentCapable
    - 프로퍼티 소스와 프로필 관리
    - 애필리케이션의 실행 환경 구성

### IoC 컨테이너의 종류
![[Pasted image 20241214161042.png]]
- BeanFactory
    - 가장 기초적인 스프링 IoC 컨테이너
- ApplicationContext
    - 기본 상태 어플리케이션 컨텍스트
- WebApplicationContext
    - ApplicationContext의 웹 버전
- ConfigurableApplicationContext
    - ApplicationContext 의 설정을 추가하거나 새로고침 할 수 있는 버전
- WebServerApplicationContext
    - 내장 웹 서버 관리용 ApplicationContext
    - 스프링부트에서 주로 사용됨.
- ReactiveWebApplicationContext
    - 리액티브 웹 애플리케이션을 위한 WebApplicationContext
    - Spring Webflux 용