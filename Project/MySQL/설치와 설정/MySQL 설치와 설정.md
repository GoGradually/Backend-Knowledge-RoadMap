[[MySQL 설치]]
[[MySQL 설정]]

# 서버 켜기
- 윈도우
	- 서버 ON : `net start MySQL80`
	- 서버 OFF: `net stop MySQL80`
- 리눅스
	- 서버 ON: `systemctl start mysqld`
	- 서버 OFF: `systemctl stop mysqld`

# 서버 접속

##### 리눅스
- `mysql -uroot -p --host=localhost --socket=/tmp/mysql.sock`
	- localhost 사용
	- 소켓 파일을 이용해서 접속한다.
	- MySQL 은 localhost 사용 시 [[IPC]]로 통신한다.
- `mysql -uroot -p --host=127.0.0.1 --port=3306
	- 127.0.0.1 사용
	- 똑같은 루프백 주소이지만, localhost와 달리 TCP/IP 통신 방식을 사용한다.
- `mysql -uroot -p`
	- 기본값 사용
	- localhost를 사용한다.
	- mysql 의 설정 파일에서 소켓 파일의 위치를 읽어 사용한다.

##### 윈도우
- `\connect --user=root --host=localhost --port=3306`
	- 리눅스와 달리 똑같이 TCP/IP로 연결됨
- `\connect --user=root --host=127.0.0.1 --port=3306`
	- 위와 같음


# DB 연결
- show, use 등을 이용해 SQL로 DB 연결 및 테이블 사용

- [[mysqld]]


