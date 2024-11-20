### CORS(Cross-Origin Resource Sharing)
- CORS는 클라이언트 측 보안정책이다. 주로 브라우저가 JS를 통해 외부 서버에 API를 요청할 때 적용된다.
- 서버에서 다른 서버로의 API요청은 CORS 정책의 적용을 받지 않는다.
  즉, 서버 대 서버 통신에서는 CORS가 브라우저 처럼 중재하지 않기 때문에 제한없이 자유롭게 통신할 수 있다.
- 한 origin(요청을 보낸 도메인)에서 실행중인 웹 어플리케이션이 다른 출처의 리소스에 접근할 수 있도록 허용하는 메커니즘
#
### CORS정책 등장 배경 
- ex) 클라이언트를 3000port, 서버를 8080port에서 실행시
```
ErrorMessage :  " XMLHttpRequest cannot load 'http://localhost:3000'. No 'Access-Control-Allow-Origin' header is present on the requested resource. 
Origin 'http://localhost:8080' is therefore not allowed access. "
```
- 요청한 도메인이 다르기 때문에 에러가 발생한다.
- 개발시 API를 사용하는 경우와 클라이언트와 서버를 분리하여 개발하는 경우도 많이 때문에   
- 해당 정책으로 인한 불편함을 해결하기 위한 정책이 CORS 정책이다.  
#
### Same-Origin Policy(동일 출처 정책)
1. 어떤 출처에서 불러 온 문서나 스크립트가 다른 출처에서 가져온 리소스와 상호작용 하는 것을 제한하는 보안방식이다.
2. 동일 출처 정책은 잠재적으로 해로올 수 있는 문서를 분리해 , 공격받을 수 있는 경로를 줄인다.
3. 웹 브라우저 보안을 위해 Protocol, Host, Port가 동일한 서버로만 ajax 요청을 주고 받을 수 있도록 한 정책이다.
   - Protocol, Host, Port (현재 페이지에서 개발자도구(f12)를 열고 "location"을 입력하면 확인가능하다.)
4. Origin(요청을 보낸 도메인)출처가 같은 서버로만 요청을 주고 받을 수 있다.
#
### 요청 방식에 따라 다른 CORS발생 여부   
1. img, video, script, link 태그 등 (기본적으로 Cross-Origin 정책을 지원한다.)
- link 태그의 href 에서 다른 사이트의 .css 리소스에 접근하는 것이 가능하다.
- img 태그의 scr 에서 다른 사이트의 .png , .jpg 등의 리소스에 접근하는 것이 가능하다.
- script 태그의 src 에서 다른 사이트의 .js 리소스에 접근하는 것이 가능
 ( type = "module" 속성은 제외)
```html
<link rel = "stylesheet" href = "..." />
<script src = "..."></script>
<img src = "..." />
```
2. XMLHttpRequest , Fetch API 스크립트 (기본적으로 Same-Origin 정책을 따른다.)
- 다른 도메인의 소스에 대해 자바스크립트 ajax 요청 API호출시
- 웹 폰트 CSS파일 내 @front-face 에서 다른 도메인의 폰트 사용시
- 자바스크립트에서의 요청은 <u>서로 다른 도메인에 대한 요청을 보안상 제한한다.</u>  
  브라우저는 기본적으로 하나의 서버 연결만 허용되도록 설정되어 있기 때문이다.
#
### CORS 에러 대응하기
1. 서버에서 "Access-Control-Allow-Origin" 응답 헤더 세팅하기
- 서버에서 "Access-Control-Allow-Origin" 헤더를 설정해서 요청을 수락할 출처를 명시적으로 지정 가능  
  이 헤더를 세팅하면 출처가 달라도 "https://example.com"의 리소스 요청을 허용한다.
```
'Access-Control-Allow-Origin': <origin> | *
```
- " * " 와일드카드 문자를 설정하면 출처에 상관없이 리소스에 접근 할 수 있지만 보안에 취약하다.

```
'Access-Control-Allow-Origin': https://example.com
```
- 위 와 같이 허용할 출처를 직접 세팅하는 것이 더 좋은 방법이다.

2. 프록시 서버 사용하기
- 프록시 서버를 사용하여 웹 애플리케이션에서 리소스로의 요청을 전달하면  
  웹 애플리케이션이 리소스와 동일한 출처에서 요청을 보내는 것 처럼 보이므로 CORS에러를 방지 할 수 있다.
- ex)  
  "http://example.com" 주소의 웹 애플리케이션이 "http://api.example.com" 리소스에서 데이터를 요청한다면  
  웹 애플리케이션은 직접적으로 리소르에 요청하는 대신 "http://example-proxy.com" 프록시 서버에 요청을 보낼 수 있다.  
  그러면 프록시 서버가 "http://api.example.com" 으로 요청을 전달하고, 응답을 다시 웹 애플리케이션에 반환한다.  
  이런 방식을 사용하면 "http://example-proxy.com" 가 요청한 것 처럼 보여 CORS에러를 방지 할 수 있다.  

  
