# 설치
- MySQL 사이트에서 설치파일 다운로드 후 설치
- 다음 세개가 필요하다
	- MySQL Server - 서버
	- MySQL Shell - 쉘
	- MySQL Router - InnoDB Cluster 용 라우팅 기능
		- 마스터-슬레이브 라우팅
- Development Computer 로 설치 (개인 테스트용)
	- 서비스용으로 설정하면 커넥션 갯수가 매우 많아짐
- 인증 방법은 MySQL 5.x 용 레거시 사용자 관리 방법 사용
	- sha2 쓰면 쓸데없이 너무 복잡해짐

# MySQL 서버 디렉토리 구조
- bin: MySQL 서버와 클라이언트 프로그램, 유틸리티 바이너리 코드를 위한 디렉토리
- include: C/C++ 헤더 파일들이 저장된 디렉터리
- lib: 라이브러리 파일들이 저장된 디렉터리
- share: 다양한 지원 파일들이 저장돼 있으며, 에러 메시지나 샘플 설정 파일(my.ini)이 있는 디렉터리


