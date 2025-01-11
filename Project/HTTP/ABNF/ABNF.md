# 구조적 설명
- HTTP를 설명하는 RFC7230문서는 ABNF (Augmented Backus-Naur Form) 로 이루어져 있다.
- RFC 1945에서 간략하게 설명하고 있고, RFC2234에서 상세하게 설명하고 있다.

### 종류
###### 구성요소
[[name = definition]]
[["literal"]]
[[파이프 - ABNF|rule1 | rule2]]
[[() - ABNF|(rule1 rule2)]]
[[애스터리스크 * - ABNF| *rule]]
[[대괄호[] - ABNF |[rule] ]]
[[<N> rule - ABNF|<N> rule]]
[[샵 - ABNF| #rule]]
[[; comment]]
###### 기본 룰
[[OCTET]]
[[CHAR]]
[[UPALPHA, LOALPHA, ALPHA]]
[[DIGIT]]
[[CTL]]
[[CRLF]]
[[Single Space|SP]]
[[HT]]
