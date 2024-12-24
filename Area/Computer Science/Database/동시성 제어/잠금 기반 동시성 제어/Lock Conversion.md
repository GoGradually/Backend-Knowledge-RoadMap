- Upgrade: S -> X Lock 변환
- Downgrade: X -> S Lock 변환

예시)
T1: 
1. S-Lock(A) 획득
2. A 읽기
3. A 수정 필요 발생
4. S-Lock을 X-Lock으로 Upgrade
5. A 수정
6. 커밋시 Lock 해제