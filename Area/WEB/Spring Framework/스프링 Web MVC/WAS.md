- 동적인 컨텐츠를 제공하기 위한 Application Server
![[Pasted image 20241215122753.png]]

### Web Server vs. WAS
- Web Server: 정적 컨텐츠 서빙용으로 이용
- WAS: 동적 컨텐츠 서빙용으로 이용
	- 단순 서빙이 아닌, 추가적인 계산이 필요한 로직에 집중


# WAS의 처리 과정
- Web Server는 웹 브라우저 클라이언트로부터 HTTP 요청을 받는다.
- Web Server는 클라이언트의 요청(HTTP Request)을 WAS에 보낸다.
- WAS는 관련된 Servlet을 메모리에 올린다.
- WAS는 web.xml을 참조하여 해당 Servlet에 대한 Thread를 생성한다. ([[Thread Pool]] 이용)
- [[HttpServletRequest]]와 [[HttpServletResponse]] 객체를 생성하여 Servlet에 전달한다.
    - Thread는 Servlet의 service() 메서드를 호출한다.
    - service() 메서드는 요청에 맞게 doGet() 또는 doPost() 메서드를 호출한다.
    - protected doGet(HttpServletRequest request, HttpServletResponse response)
- doGet() 또는 doPost() 메서드는 인자에 맞게 생성된 적절한 동적 페이지를 Response 객체에 담아 WAS에 전달한다.
- WAS는 Response 객체를 HttpResponse 형태로 바꾸어 Web Server에 전달한다.
- 생성된 Thread를 종료하고, HttpServletRequest와 HttpServletResponse 객체를 제거한다.

![[Pasted image 20241215122825.png]]