기본 Lock:
- S: Shared Lock
- X: Exclusive Lock

# Intention Lock
- IS: Intention Shared
	- 하위 레벨에서 S 락을 걸기 위한 의도
- IX: Intention Exclusive
	- 하위 레벨에서 X 락을 걸기 위한 의도
- SIX: Shared and Intention Exclusive
	- 현재 레벨은 S 락, 하위 레벨에 X 락을 걸기 위한 의도

# Lock 호환성 매트릭스
   IS   IX  S   SIX    X
IS   O O  O   O   X
IX   O   O   X   X   X
S    O   X   O   X   X
SIX O   X   X   X    X
X    X   X   X   X    X

O: 호환됨 (Compatible)
X: 호환되지 않음 (Incompatible)



# 프로토콜 규칙
1) Root에서 leaf 방향으로 락 획득
2) 상위 노드의 intention 락 없이 하위 노드 락 획득 불가
3) Bottom-up 방식으로 락 해제
4) 2PL 프로토콜 준수


# 장점
- 동시성 향상
- 락 관리 오버헤드 감소
- 유연한 락 운영 가능

# 단점
- 구현 복잡도 증가
- 데드락 가능성 여전히 존재
- [[Lock escalation]] 처리 필요