- 핸들러 어댑터와 핸들러 사이에 있는
	- HTTP 메시지와 JAVA 객체 간 변환을 돕는 컨버터
- 핸들러 어댑터가 핸들러를 호출하기 전, 파라미터를 변환하기 위해 사용한다.
- ArgumentResolver 와 ReturnValueHandler 를 호출하여, 자바 객체와 HTTP 메시지 간의 변환을 돕는다.


### HTTP 메시지 컨버터를 사용하는 경우
- HTTP 요청
	- @RequestBody
	- RequestEntity<>
- HTTP 응답
	- @ResponseBody
	- ResponseEntity<>
### HTTP 메시지 컨버터의 구조
- canRead()
	- 메시지 컨버터가 해당 클래스를 읽을 수 있는지
		- 대상 클래스 타입을 지원하는가
		- HTTP 요청의 Content-Type 미디어 타입을 지원하는가
- canWrite()
	- 메시지 컨버터가 해당 클래스 형태로 쓸 수 있는지
		- 대상 클래스 타입을 지원하는가
		- HTTP 요청의 Accept 미디어 타입을 지원하는가
			- @RequestMapping의 produces 도
- read()
	- 메시지 컨버터를 통해 메시지를 읽는 기능
		- 역직렬화 기능
- write()
	- 메시지 컨버터를 통해 객체를 메시지로 쓰는 기능
		- 직렬화 기능
### 스프링부트 기본 메시지 컨버터
- ByteArrayHttpMessageConverter
	- byte[] 데이터 처리
		- 클래스 타입
			- byte[]
		- 미디어 타입
			- \*/\*
		- 요청 예
			- @RequestBody byte[] data
		- 응답 예
			- @ResponseBody return byte[]
			- Content-type: application/octet-stream
- StringHttpMessageConverter
	- String 데이터 처리
		- 클래스 타입
			- String
		- 미디어 타입
			- \*/\*
		- 요청 예
			- @RequestBody String data
		- 응답 예
			- @ResponseBody return "ok"
			- Content-Type: text/plain
- MappingJackson2HttpMessageConverter
	- JSON 데이터 처리
		- 클래스 타입
			- 객체
			- HashMap
		- 미디어 타입
			- application/json 관련
		- 요청 예
			- @RequestBody HelloData data
		- 응답 예
			- @ResponseBody return helloData
			- Content-Type: application/json 관련
				
### 메시지 컨버터 동작 방식
1. 컨트롤러에서 메시지를 읽거나 쓸 때, HTTP 메시지 컨버터를 사용하는 파라미터를 사용하면
2. 메시지 컨버터가 해당 메시지를 읽을/쓸 수 있는지 canRead() / canWrite() 메소드를 호출한다
3. 조건을 만족하면 read() / write() 메소드를 호출한다.
	- 적절하게 읽고, 쓴다.
### 메시지 컨버터의 동작 위치
- 핸들러 어댑터 - 핸들러 사이!
	- 핸들러 어댑터 -> 핸들러 사이(요청)
		- Argument Resolver
	- 핸들러 -> 핸들러 어댑터 사이(응답)
		- ReturnValue Handler
	- 둘 다 인터페이스로 구성됨
### 확장
- HandlerMethodArgumentResolver
- HandlerMethodReturnValueHandler
- HttpMessageConverter
- 셋 모두 인터페이스로 구성되어 있어서, 사용지 지정 확장 가능
	- WebMvcConfigurer 를 상속 받아서 스프링 빈으로 등록
	- 실제 확장할 때 WebMvcConfigurer 검색해서 사용해보기


[[HTTP 메시지 컨버터를 사용하는 기능]]