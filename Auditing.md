### 사용처
- 엔티티를 생성 변경할 때
	- 변경한 사람과 시간을 추적하고 싶으면?
		- 등록일
		- 수정일
		- 등록자
		- 수정자

### Auditing 적용
- 지정한 필드가 특정 시점에 값을 저장하도록 설정
	- 메소드를 만들어서, 특정 시점에 해당 필드에 값을 대입한다!
- 공통 사전 설정
	- @EnableJpaAuditing
		- Jpa 의 감시모드 켬
		- 스프링부트 config 클래스에 적용![[Pasted image 20241215212238.png]]
	- @EntityListeners(AuditingEntityListener.class)
		- 엔티티가 Auditing 받는다는걸 선언
			- 감시 리스트에 추가
		- 베이스 엔티티에 적용![[Pasted image 20241215212253.png]]
- @CreatedDate
	- 생성 시점 저장
	- LocalDateTime![[Pasted image 20241215212310.png]]
- @LastModifiedDate
	- 마지막 변경 시점 저장
	- LocalDateTime![[Pasted image 20241215212326.png]]
- 등록자, 수정자 사전 설정
	- 등록자, 수정자 처리용 AuditorAware 메소드 or 구현체를 빈에 등록![[Pasted image 20241215212351.png]]
	- 실무에서는 ID 가져와서 저장
		- 세션 정보나
		- 스프링 시큐리티 로그인 정보에서
			![[Pasted image 20241215212405.png]]
- @CreatedBy
	- 생성 시점에 해당 필드에 값을 저장한다
	- AuditorAware 메소드를 수행한다.![[Pasted image 20241215212426.png]]
- @LastModifiedBy
	- 업데이트 시점에 해당 필드에 값을 저장한다
	- AuditorAware 메소드 수행![[Pasted image 20241215212448.png]]

### 실제 사용
- 해당 BaseEntity를 상속받아서 기능을 사용한다.
- 실무에서는 등록자, 수정자가 반드시 필요하진 않을 수 있기 때문에
	- BaseEntity 와 BaseTimeEntity 를 분리해서 사용한다
### 전체 엔티티에 Auditing 적용 방법
- META-INF/orm.xml 에 옵션 지정
- 복사 붙여넣기 해서 쓰기