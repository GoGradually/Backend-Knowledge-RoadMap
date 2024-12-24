# Two-Phase Locking 이란?
트랜잭션의 Lock 연산을 2개의 Phase로 나누어 관리:
### Phase 1) Growing Phase (확장 단계)
- Lock만 획득 가능
- Lock 해제는 불가능

### Phase 2) Shrinking Phase (수축 단계)
- Lock 해제만 가능 
- 새로운 Lock 획득 불가능


### 2PL의 변형
1) Strict 2PL
- 모든 Exclusive Lock을 트랜잭션 커밋 시점까지 유지
- Cascading Rollback 방지
- 대부분의 DBMS가 채택하는 방식

2) Rigorous 2PL
- 모든 Lock(Shared, Exclusive)을 커밋 시점까지 유지
- 가장 엄격한 형태
- 트랜잭션들이 커밋 순서대로 정렬됨을 보장


# 추가 기능 - [[Lock Conversion]]


# 장점
- Serializability 보장 
	- **잠금 시점 기준으로 트랜잭션을 정렬**할 수 있음
- 구현이 상대적으로 단순 
- 직관적인 이해 가능

# 단점
- Deadlock 발생 가능 
- 긴 트랜잭션이 있을 경우 동시성 저하 
- Lock 관리 오버헤드


# 실제 구현 시 고려사항
### Lock Manager 구현
- Hash table 기반의 Lock table 유지
- 트랜잭션별 Lock 정보 관리
- deadlock 감지 필요

### 성능 최적화
- Lock 획득/해제의 오버헤드 최소화
- 적절한 Lock 단위([[Granularity]]) 선택
- 필요한 경우 Lock 우회 기법 검토