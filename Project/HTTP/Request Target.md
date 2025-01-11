# 구조적 설명
- request-target = origin-form / absolute-form / authority-form / asterisk-form

- origin-form = absolute-path [ "?" query ]
	- 기본 폼
- absolute-form = absolute-URI
	- 절대 경로
- authority-form = authority
	- [[HTTP CONNECT | CONNECT 리퀘스트]]에서만 사용
	- 호스트 이름 + 포트 번호
- asterisk-form = "\*"
	- 다음과 같이 쓰일 수 있음
	- OPTIONS * HTTP/1.1
- 다음 request가
```HTTP
OPTIONS http://www.example.org:8001 HTTP/1.1
```
- 다음과 같이 변환될 때 쓰임
```HTTP
OPTIONS * HTTP/1.1 
Host: www.example.org:8001
```

