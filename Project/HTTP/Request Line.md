# 구조적 설명
- [[HTTP Request]] 의 첫 줄을 담당하는 line.
- 다음과 같은 구조를 갖는다.
[[HTTP Method|method]] [[Single Space|SP]] [[Request Target|request-target]] [[Single Space|SP]] [[HTTP 버전|HTTP-version]] [[CRLF]]
### 요청 라인의 파싱
- 수신자는 요청 라인을 컴포넌트로 분리하기 위해 공백을 기준으로 나눔
- 일부 사용자는 하이퍼텍스트

# 논리적 설명