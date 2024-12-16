- 지정한 메소드가 특정 시점에 실행되도록 설정
- @PrePersist
	- 영속성 컨텍스트에 처음 추가되기 전
- @PostPersist
	- 영속성 컨텍스트에 처음 추가되고 난 후
- @PreUpdate
	- 값이 수정되기 직전
- @PostUpdate
	- 값이 수정되고 난 후
- 사용 방법
	- 시간을 저장하는 Base 엔티티 만들기
		![[Pasted image 20241215212115.png]]
		- @MappedSuperclass
	- 추적할 엔티티에 해당 Base엔티티 상속받기
		![[Pasted image 20241215212133.png]]