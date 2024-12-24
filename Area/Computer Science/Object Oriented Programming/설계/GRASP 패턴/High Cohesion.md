- 클래스가 단일하고 잘 정의된 목적을 가지도록
- 클래스의 책임이 밀접하게 연관되어 있고 집중되어 있어야 함
- [[SRP]]

![[Pasted image 20241211155049.png]]
- 이것보다
	- Register가 Controller + Sale 에 Payment 등록
![[Pasted image 20241211155200.png]]
- 이게 낫다!
	- Register 컨트롤러 역할에 집중
	- Sale 이 직접 Payment 생성해서 등록

- 메소드 이름에 집중하지 말고
- 정보와 책임에 집중해라.