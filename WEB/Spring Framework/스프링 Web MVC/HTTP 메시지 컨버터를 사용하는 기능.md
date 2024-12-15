### @RequestBody
- HTTP 요청 JSON 메시지 바디 -> 객체로 변환
### @ResponseBody
- 응답 객체 -> HTTP 응답 JSON 메시지 바디로 변환
### HttpEntity
- 동적으로 응답 코드를 설정해야 할 떄 사용하는 클래스
- 제네릭 특성 상 메시지 컨버터가 자동으로 Json 문자열로 변환됨
### RequestEntity

- HttpEntity를 상속받은 클래스
	- request 쪽 어노테이션이 워낙 잘되어있어서 잘 안쓰인다.
		- [[@PathVariable]]
		- [[@RequestBody]]
		- [[@RequestParam]]
		- [[@ModelAttribute]]
### ResponseEntity
- 주요 용도
	- 상태 코드 동적 제어
		- API 통신 시 사용!
	- 응답 헤더 커스터마이징
	- 응답 본문 다양한 방식으로 설정
	- 유연한 응답 구성
### 사용자 지정
- 커스텀 HTTP 메시지 컨버터를 정의하여 다른 형식의 Content Type 도 메시지 컨버팅을 할 수 있다.