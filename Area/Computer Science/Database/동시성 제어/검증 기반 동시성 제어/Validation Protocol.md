# 검증 기반 규약이란?
- 트랜잭션이 실행되는 동안 병렬로 진행
- 마지막에 검증을 통해 일관성 확인
- "낙관적 동시성 제어" 라고도 불림
	- 낙관적 락과 비슷한 경우에 사용
	- 충돌이 적을 것이라 예상되는 경우
	- 하지만 최소한의 안전장치는 필요한 경우

# 검증 기반 규약의 단계
1. **읽기 단계 (Read Phase)**
    - 트랜잭션은 데이터베이스의 데이터를 읽어들여 **로컬 변수**에 저장
    - 데이터 쓰기 작업은 **임시 변수**에서 수행되며, 데이터베이스는 실제로 수정되지 않음
    - 이 단계는 병렬적으로 여러 트랜잭션이 실행될 수 있음
2. **검증 단계 (Validation Phase)**
    - 트랜잭션이 읽기 단계를 마치면 **검증 테스트** 수행
    - 검증 테스트는 현재 트랜잭션이 **직렬 가능성(serializability)**을 유지하는지를 확인
    - 검증에 실패한 트랜잭션은 롤백
3. **쓰기 단계 (Write Phase)**
    - 검증이 성공하면, 트랜잭션이 임시 변수에 저장한 데이터를 데이터베이스에 적용
    - **읽기 전용 트랜잭션은 이 단계를 생략**

# 검증 테스트 알고리즘
![[Pasted image 20241221192012.png]]
- TS(Tk) < TS(Ti) 에 대하여
	1. FinishTS(Tk) < StartTS(Ti)
	2. WS(Tk) 와 RS(Ti) 간 교집합이 없고, && FinishTS(Tk) < ValidationTS(Ti)
		- 교집합이 있으면? Ti 가 더티 리드가 발생할 수 있음
		- FinishTS(Tk) >= ValidationTS(Ti) 이면? Tk가 읽은 데이터가 더티 리드일 수 있음

트랜잭션 Ti의 검증 단계에서, 다른 트랜잭션들과의 충돌 여부를 아래의 규칙에 따라 검사
1. **Ti가 읽기-쓰기 충돌을 확인**
    - 트랜잭션 `Tk`가 `Ti`의 `ValidationTS(Ti)` 이전에 쓰기를 완료(`FinishTS(Tk)`)했다면:
        - `WS(Tk)`와 `RS(Ti)` 간 교집합이 없어야 합니다.
        - 이유: `Tj`가 데이터를 변경한 후에, `Ti`가 동일 데이터를 읽었다면 데이터 일관성에 문제가 생깁니다.
2. **쓰기-쓰기 충돌을 확인**
    - 트랜잭션 `Tk`가 아직 쓰기를 완료하지 않았다면 (`ValidationTS(Tk)` ≥ `ValidationTS(Ti)`):
        - `WS(Tj)`와 `WS(Ti)` 간 교집합이 없어야 합니다.
        - 이유: `Tj`와 `Ti`가 동일 데이터를 쓰려고 하면 데이터 충돌이 발생합니다.
3. **쓰기가 완료된 데이터의 유효성 확인**
    - 이미 쓰기를 완료한 트랜잭션의 결과가 `Ti`의 읽기 집합에 영향을 주었는지 확인.