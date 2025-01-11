# 구조적 설명
- HTTP 메시지는 [[HTTP Request|요청]]과 [[HTTP Response|응답]]으로 구분된다.

# 논리적 설명
### 기본 메시지 포맷
```HTTP
start-line 
*( header-field CRLF ) 
CRLF 
[ message-body ]
```

### Start Line
- HTTP 메시지의 첫 줄
- [[Request Line]] 혹은 [[status line]] 을 형태로 갖는다.

### 헤더 필드


### [[HTTP 메시지 바디|메시지 바디]]

###### 예시
```http
GET /hello.txt HTTP/1.1
User-Agent: curl/7.16.3 libcurl/7.16.3 OpenSSL/0.9.7l zlib/1.2.3 
Host: www.example.com 
Accept-Language: en, mi
```

```HTTP
HTTP/1.1 200 OK 
Date: Mon, 27 Jul 2009 12:28:53 GMT 
Server: Apache 
Last-Modified: Wed, 22 Jul 2009 19:15:56 GMT 
ETag: "34aa387-d-1568eb00" 
Accept-Ranges: bytes 
Content-Length: 51 
Vary: Accept-Encoding 
Content-Type: text/plain 

Hello World! My payload includes a trailing CRLF.
```

