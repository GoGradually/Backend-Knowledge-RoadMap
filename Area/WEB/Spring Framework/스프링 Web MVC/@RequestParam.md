- HTTP 요청의 파라미터를 메소드의 파라미터로 바인딩
- 주요 용도
	- URL 쿼리 파라미터 추출
	- 바디의 Form 데이터 접근
	- 필수 파라미터 지정
		- 이 값 없으면 에러를 발생시키도록
		- required=false
	- 기본값 설정
		- 주어지지 않았을 떄, 기본값으로 특정 값을 지정할 수 있다
		- 반드시 문자열이어야 함
	- 파라미터 이름 매핑
		- 메소드 파라미터 이름과 요청 파라미터 이름이 다를 경우, 매핑 가능