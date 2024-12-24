### HttpServletRequest란?
- HTTP 메시지를 파싱해서 HttpServletRequest 객체에 담아서 제공해주는 서블릿 컨테이너의 기능
- 임시 저장소 기능 제공
	- 해당 HTTP 요청이 시작될 때부터 끝날 때까지 유지되는 임시 저장소 기능
	- 저장
		- request.setAttribute(name, value)
	- 조회
		- request.getAttribute(name)
- 세션 관리 기능 제공
	- request.getSession(create: true)


### HttpServletRequest 기본 사용법
- 서블릿 request
	- 쿼리 스트링 꺼내기
		- request.getParameter("username")
	- 메소드 꺼내기
		- request.getMethod()
	- 프로토콜 꺼내기
		- request.getProtocol()
	- URL 꺼내기
		- request.getRequestURL()
	- https 유무
		- request.isSecure()
- 헤더
	- 헤더 조회
		- request.getHeader("헤더 이름")
	- 편리한 헤더 조회
		- request.getXxxx()
- 바디
	- form 파라미터 형식 조회
	- message body 데이터 직접 조회


### HTTP Request 메시지 생성 방식
##### GET - 쿼리 파라미터
- 특징
	- 메시지 바디 없이 URL 의 쿼리 파라미터에 데이터를 포함해서 전달
- 단일 파라미터 조회
	- request.getParameter(Key)
- 파라미터 이름들 모두 조회
	- request.getParameterNames()
- 복수 파라미터 조회
	
	- request.getParameterValues()
		
- 파라미터를 Map 으로 모두 조회
	
	- request.getParameterMap()
		
##### POST - HTML Form
- 특징
	- content-type: application/x-www-form-urlencoded
	- 메시지 바디에 쿼리 파라미터 형식으로 데이터를 전달함.
- 단일 파라미터 조회
	- request.getParameter(Key)
- 파라미터 이름들 모두 조회
	- request.getParameterNames()
- 복수 파라미터 조회
	- request.getParameterValues()
- 파라미터를 Map 으로 모두 조회
	- request.getParameterMap()
##### HTTP Message body - JSON
- 특징
	- content-type: application/json
	- 그냥 문자열임
- json 결과를 사용할 수 있는 자바 객체로 변환하려면
	- Jackson, Gson 같은 Json 변환 라이브러리 추가해서 사용해야 함
		- 그냥 Jackson 쓰자

- 위 기능들의 추상화 : [[HTTP 메시지 컨버터]]