```
"#"으로 정의되어 있는 구조는 *과 비슷하다. 차이점은 요소들간의 구분을 "," 혹은
LWS(Linear White Space)로 한다. <n>#<m>element는 요소가 n개에서
m개 존재할 수 있다는 의미이다. "( *LWS element *( *LWS "," *LWS element ))"는
1#element와 같은 의미를 갖는다. (element), , (element)와 같이 표기하면
null element를 의미하지만, 요소를 셀때는 포함이 되지 않는다.

예를들어, 1#2(3ALPHA)라 하면 ABC, ,DEF라 표기해도 문제되지 않는다. null 요소까지
생각하면 3개이지만 null요소는 포함시키지 않기 때문이다. 여기서도 또한 <n>, <m>은
0을 포함하여 어떤 숫자도 들어갈 수 있다.
```

