![[Pasted image 20241215185555.png]]
### 디스패처 서블릿
- 프론트 컨트롤러
- 모든 경로에 대해 매핑하여, 모든 HttpServlet 을 강탈한다.
- doDispatch() 메소드를 통해 모든 과정을 거쳐, view 로 반환한다.
### 핸들러 매핑
- 들어온 URL에 대해 적절한 핸들러가 있는지 매핑 정보를 조회한다.
- 핸들러 매핑 방식의 우선순위
	- RequestMappingHandlerMapping
		- @RequestMapping 탐색
	- BeanNameUrlHandlerMapping
		- 스프링 빈의 이름으로 탐색
### 핸들러 어댑터 목록 탐색 객체
- 탐색한 핸들러에 맞는 파라미터를 제공할 수 있도록, 
- 핸들러 어댑터 선택 우선순위
	- RequestMappingHandlerAdapter
		- @RequestMapping 객체 어댑터
	- HttpRequestHandlerAdapter
		- HttpRequestHandler 객체 어댑터
	- SimpleControllerHandlerAdapter
		- SimpleControllerHandler 객체 어댑터
- 핸들러 어댑터의 support() 함수를 호출하여, 해당 핸들러 어댑터가 사용 가능한지를 확인한다.
### 핸들러 어댑터
- 실제 핸들러를 호출하는 어댑터 패턴
- 탐색한 핸들러 어댑터를 통해 HTTP 메시지를 변환하고, handle() 메소드를 통해 핸들러를 호출.
### 핸들러
- 실제 컨트롤러 역할을 수행하는 컨트롤러
### [[HTTP 메시지 컨버터]]
- 핸들러 어댑터와 핸들러 사이에 있는
	- HTTP 메시지와 JAVA 객체 간 변환을 돕는 컨버터
- 핸들러 어댑터가 핸들러를 호출하기 전, 파라미터를 변환하기 위해 사용한다.

### [[ExceptionResolver]]

### 뷰 리졸버
- 전달받은 viewName 문자열을 view의 경로로 로 변환하는 역할
### 뷰
- 클라이언트 화면 담당
- 렌더링 수행