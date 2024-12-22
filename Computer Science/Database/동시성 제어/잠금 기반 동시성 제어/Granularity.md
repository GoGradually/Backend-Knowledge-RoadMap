# Multiple Granularity가 필요한 이유
문제 상황:
- 전체 테이블을 읽어야 하는 트랜잭션
- 단 하나의 row만 수정하는 트랜잭션

기존 방식의 문제:
- 테이블 전체 락: row 단위 작업에 너무 제한적
- row 단위 락: 테이블 전체 작업시 오버헤드 큼

해결책:
- 계층적 락킹 구조 도입
- DB -> Table -> Page -> Row 등 여러 단계의 락 지원


# 락의 계층 구조
DB Level
  ├── Area/Schema Level
  │    ├── Table Level
  │    │    ├── Page Level
  │    │    │    └── Row Level
  │    │    └── Index Level
  │    └── Another Table
  └── Another Area



# 예시 - [[Intention Lock 모드]]
