- 빈 등록을 자동으로 수행해주는 기능
- 스프링 프레임워크의 [[@Conditional]] 기능을 확장해서 구현한다.

# 기본적 동작 원리
1. 스프링부트가 관리하는 모든 프로젝트는 AutoConfigure 프로젝트에 의존성을 갖는다.
2. 스프링부트는 스프링 컨테이너 초기화 시 등록해야 하는 빈에 AutoConfigure 로 등록된 빈들을 추가한다.
3. 
![[Pasted image 20241223192120.png]]



# 임시
@AutoConfiguration
@ConditionalOnXxx
@Import
ImportSelector
