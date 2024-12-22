### WAR 란?
- WAR(Web Application Archive)
- 웹 애플리케이션 서버에 배포할 때 사용하는 파일
- WAS 위에 실행되기 위해 최적화된 파일 형식
- 아래와 같은 구조를 반드시 따라야 한다.![[Pasted image 20241218172514.png]]
### WAR 구조
- `WEB-INF`
	- **`classes` : 실행 클래스 모음**
	- **`lib` : 라이브러리 모음**
	- `web.xml` : 웹 서버 배치 설정 파일(생략 가능)
- `index.html` : 정적 리소스
- `WEB-INF` 폴더 하위는 자바 클래스와 라이브러리, 그리고 설정 정보가 들어가는 곳이다.
- `WEB-INF` 를 제외한 나머지 영역은 HTML, CSS 같은 정적 리소스가 사용되는 영역이다