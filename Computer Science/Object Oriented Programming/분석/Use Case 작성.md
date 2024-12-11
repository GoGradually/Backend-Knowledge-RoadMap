- [[Use Case]]란?

### 작성 목적
- 도메인 프로세스는 무엇인가?
- 기능 요구사항은 무엇이 있는가?

- 하나의 프로젝트에는 여러개의 Use Case 가 존재한다
- 하나의 Use Case내에는 여러개의 시나리오가 존재한다
### 작성 과정
1. Actor 정의
	- **actor 와 그 actor 의 goal** 뿐만 아니라
	- **stakeholder 와 그들의 interest** 도 같이 고려해야 한다.
2. 시스템 바운더리 설정
	- 어디까지를 이 Use Case 의 시스템 내부로 볼 것인가?
	- 어디까지만 고려해서 작성할 것인가?
	- 바운더리에 따라 Use Case 가 달라진다.
3. 메인(성공) 시나리오 작성
4. 도식화를 위한 FSM 추가
5. 실패 시나리오 작성

- Use Case 가 지나치게 커지면
    - 하나의 Use Case를 여러개의 Use Cases로 분리한다.
- 좋은 Use Case 의 크기
    - EBP(Elementary Business Processes) 정도
    - 사용자가 이용하는데 5분정도 걸릴 정도
    - Why & How 로 조절
        - Why
            - Goal level UP - 좀 더 큰 단위로 키우기
        - How
            - Goal level DOWN - 좀 더 작은 단위로 쪼개기
	    ![[Pasted image 20241211104707.png]]
	- 높은 Goal 레벨은 Context 정보를 파악하기 쉽게 하지만, 추상적인 정보만 제공하고
	- 낮은 Goal Level은 실제 동작을 이해하기 쉽게 하지만, 큰 그림을 보기 어렵게 한다.

