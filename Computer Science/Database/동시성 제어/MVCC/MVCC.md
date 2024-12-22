# 다중 버전 동시성 제어 (MultiVersion Concurrency-Control)
특징:
- 데이터 아이템의 여러 버전을 유지
- 읽기 작업이 쓰기 작업을 블록하지 않음
- 각 버전은 타임스탬프로 구분됨
- 읽을 때, 버전이라는 새로운 기준을 추가해서 읽음

### 버전의 삭제
- 버전 두개가 있을 시, 두 버전 모두 가장 오래된 트랜잭션의 타임 스탬프보다 작거나 같으면
- 둘 중 한 버전(더 오래된 버전)은 사용되지 않으므로, 삭제할 수 있음


# 응용 1: MultiVersion Timestapmp Ordering([[MVTO]])


# 응용 2: Multiversion Two-Phase Locking([[MV2PL]])