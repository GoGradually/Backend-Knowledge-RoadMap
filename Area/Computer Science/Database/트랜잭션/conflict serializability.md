- Conflict Serializability
    - 직렬 스케줄과 충돌 동등한가?
    - 파악하는 방법
        - 한 스케줄에 대하여, 스케줄 내 트랜잭션을 DAG 화!
	        - ![[Pasted image 20241222224114.png]]
            - 정점
                - 스케줄 내 트랜잭션
            - 간선
                - 트랜잭션 간 어떠한 데이터에 대하여 연산의 순서
                - T1: Write(D) -> T2: Read(D)
                - T1: Read(D) -> T2: Write(D)
                - T1: Write(D) -> T2: Write(D)
        - 해당 DAG의 위상정렬 = Serializability Order!
	        - ![[Pasted image 20241222224146.png]]
        - 사이클이 있으면-> 직렬가능하지 않음
	        - ![[Pasted image 20241222224200.png]]
    - 주의) 같은 결과를 낸다고, 항상 충돌 동등한 것은 아니다.
	    - ![[Pasted image 20241222224212.png]]