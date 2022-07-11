# URL 이란?

**URL**은 **Uniform Resource Locator**로 이름 그대로 네트워크 상에 있는 인터넷 자원의 위치를 나타내는 주소이다.  

</br>

> ### URL 문법
> - 가장 앞에 접근할 프토로콜을 적는다. ex) => http, ftp
> - 프로토콜명이 끝나면 ':'(콜론)을 쓴다. ex) => http:  , ftp:
> - 뒤에 IP, 인터넷 주소가 오는경우 "//"를 적어준다.  ex) => http://www.naver.com

</br>

> ### Java.net의 URL class를 생성할 때 2가지 방법  
> - URL url = new URL(String spec) -> 문자열을 받아서 처리하는 방법으로 많이 쓰이는 방법이다.  
>  ex) new URL("https://www.naver.com/")  
> - URL url = new URL(String protocol, String host, int port, String file) -> 프로토콜, 호스트, 포트, 파일명등을 받아서 처리하는 방법  
>  ex) new URL("https", "www.naver.com", 80, "filename")  

</br>

# URLConnection 이란?  
**URLConnection**은 URL을 통해 통신하는 프로그램을 **JAVA**를 사용해 개발할 때 사용한다.  
URL만 알고 있다면 HTTP 요청 및 응답 전송, 검색, 데이터 읽기 등이 가능한 코드를 만들 수 있다.                                           
 **URLConnection**과 **HttpURLConnection** 클래스 등을 사용한다.  
 <br>
 > - **URLConnection JAVA11 SPEC**<br>
 > [https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/net/URLConnection.html](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/net/URLConnection.html)
 > <br>
 > 
> - **HttpURLConnection JAVA11 SPEC** <br>
 > [https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/net/HttpURLConnection.html](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/net/HttpURLConnection.html)


 <br><br>
 
 ## HttpURLConnection의 예시 
 <br>
 
 > **NAVER에서 안녕을 검색했을 때의 화면**
 </br>
 <img width="75%" height="75%" alt="네이버_안녕검색화면" src="https://user-images.githubusercontent.com/67998815/153976659-0b7a0a13-e890-4deb-ab92-c340c30bded6.PNG">  
 </br>
 
 > **Code**  </br>
 
 </br>
<img width="80%" height="80%" alt="네이버_안녕검색코드" src="https://user-images.githubusercontent.com/67998815/153979911-d485c682-2743-45b5-93c3-7e1be141e33e.PNG">

</br>

> **읽어오는 html 데이터** </br>

</br>

```
"data": "<!doctype html>   
<html lang=\"ko\" data-dark=\"false\"> 
<head> <meta charset=\"utf-8\"> <title>NAVER</title> <meta http-equiv=\"X-UA-Compatible\" content=\"IE=edge\"> 
<meta name=\"viewport\" content=\"width=1190\"> <meta name=\"apple-mobile-web-app-title\" content=\"NAVER\"/>   
<meta name=\"robots\" content=\"index,nofollow\"/>    
<meta name=\"description\" content=\"네이버 메인에서 다양한 정보와 유용한 컨텐츠를 만나 보세요\"/> <meta property=\"og:title\" content=\"네이버\">   
<meta property=\"og:url\" content=\"https://www.naver.com/\">   <metaproperty=\"og:image\"content=\"https://s.pstatic.net/static/www/mobile/edit/2016/0705/mobile_212852414260.png\">   
<meta property=\"og:description\" content=\"네이버 메인에서 다양한 정보와 유용한 컨텐츠를 만나 보세요\"/>  

                                                       (중략)
       
<h3 class=\"blind\">네이버 정책 및 약관</h3> 
<ul class=\"list_corp\"> <li class=\"corp_item\">
<a href=\"https://www.navercorp.com\" data-clk=\"intronhn\">회사소개</a></li> 
<li class=\"corp_item\"><a href=\"https://recruit.navercorp.com/naver/recruitMain\" data-clk=\"recruit\">인재채용</a></li> <li class=\"corp_item\">
<a href=\"https://www.navercorp.com/naver/proposalGuide\" data-clk=\"contact\">제휴제안</a></li> <li class=\"corp_item\">
<a href=\"/policy/service.html\" data-clk=\"service\">이용약관</a></li> <li class=\"corp_item\">
<a href=\"/policy/privacy.html\" data-clk=\"privacy\"><strong>개인정보처리방침</strong></a></li> <li class=\"corp_item\">
<a href=\"/policy/youthpolicy.html\" data-clk=\"youth\">청소년보호정책</a></li> 
<li class=\"corp_item\"><a href=\"/policy/spamcheck.html\" data-clk=\"policy\">네이버 정책</a></li> 
<li class=\"corp_item\"><a href=\"https://help.naver.com/\" data-clk=\"helpcenter\">고객센터</a></li> </ul> <address class=\"addr\">
<a href=\"https://www.navercorp.com\" target=\"_blank\" data-clk=\"nhn\">ⓒ NAVER Corp.</a></address> 
</div> </div> </div> </div> <div id=\"adscript\" style=\"display:none\"></div> </body> </html>"
```

</br>

 ## URLConnection 생성 과정  
 
 **1. URL 객체 생성하기**
 
 ```
 URL url = new URL("https://www.naver.com");
 ```
 
 **2. URL에서 URLConnection 객체 얻기**
 
 ```
 URLConnection con = url.openConnection(); // urlConnection 객체 생성
 HttpURLConnection con = (HttpURLConnection) url.openConnection(); // 형변환을 통한 HttpURLConnection 객체 생성
 HttpsURLConnection con = (HttpsURLConnection) url.openConnection(); // 형변환을 통한 HttpsURLConnection 객체 생성
 ```  
 
 > URLConnection 클래스는 생성자가 protected로 선언되어있기 때문에 직접 객체생성은 할 수 없다.  
 > openConnection() 메서드가 리턴하는 URLConnection 객체를 사용하거나 형변환하여 HttpURLConnection 등으로 사용할 수 있다.
 
 </br>

 **3. URLConnection 요청 방식 설정**  
 
 > 클라이언트와 서버, 서버와 서버 등의 연결을 설정하기 전 다양한 옵션을 설정할 수 있다.    
 
#### - URLConnection Method

```
 - setConnectTimeout (int timeout) : 연결 타임아웃 값을 설정 (단위: millisecond)
 
 - setReadTimeOut (int timeout) : 읽기 타임아웃 값을 설정 (단위: millisecond)
 
 - setDefaultUseCaches (boolean default) : 기본 캐시 사용여부를 설정(기본값: true) 
 
 - setUseCaches (boolean useCaches) : 연결이 캐시를 사용하는지 여부를 설정(기본값: true)
 
 - setDoInput (boolean doInput) : URLConnection을 서버에서 컨텐츠를 읽는 데 사용가능한지 설정(기본값: true)
 
 - setDoOutput (boolean doOutput) : URLConnection이 서버에 데이터를 보내는 데 사용할 수 있는지 여부를 설정(기본값: false)
 
 - setIfModifiedSince (long time) : 클라이언트가 검색한 컨텐츠의 마지막 수정 시간을 설정. 서버가 저장된 시간 이후에 
                                    정적컨텐츠가 변경되지 않았다면 업데이트하지않고 304(수정되지 않음)를 반환
 
 - setAllowUserInteraction (boolean allow) : 사용자 상호작용을 활성 또는 비활성(기본값 false)
 
 - setDefaultAllowUserInteraction (boolean default) : 이후 모든 URLConnection객체에 대한 사용자 상호작용의 기본값 설정
 
 - setRequestProperty (String key, String value) : KEY = VALUE 쌍으로 지정된 일반 요청 속성을 설정. 
                                                   이미 같은 KEY가 있는 경우 이전 값을 새 값으로 덮어씌움 
```   


#### - HttpURLConnection Method  

> URLConneciton의 하위 클래스인 HttpURLConnection 클래스는 HTTP관련 기능을 사용한 연결 구성을 위한 메서드를 제공

```
 - setRequestMethod (String method) : HTTP Method인 GET, POST, PUT, PATCH, DELETE, HEAD 등을 설정

 - setChunkedStreamingMode (int chunkLength) : 청크 분할 전송 인코딩. 컨텐츠의 길이를 모를 경우 사용. 
                                               내부 버퍼링 없이 HTTP Request 본문을 스트리밍 한다

 - setFixedLengthStreamingMode (long contentLength) : 컨텐츠의 길이를 알고 있는 경우 사용. 
                                                      내부 버퍼링 없이 HTTP Request 본문을 스트리밍 한다 

 - setFollowRedirects (boolean follow) : 이 Static Method는 true로 설정시 HttpURLConnection 객체가 리다이렉트를 따라가고, 
                                         false시 따라가지 않는다(기본값 : true)
 
 - setInstanceFollowRedirects (boolean follow) : 리다이렉션 후 HttpURLConnection 클래스의 인스턴스가 따라가야하는지를 설정. 
                                                 미설정시 setFollowRedirects를 따름(기본값 : true)
```

</br>

 **4. 헤더필드 읽기**  
 
 ```
 - getHeaderFields () : 모든 헤더필드를 포함한 맵 반환

 - getHeaderField (int n) : n번째 헤더 필드의 값 반환

 - getHeaderField (String name) : 해당 이름의 헤더필드를 반환

 - getHeaderFieldKey (int n) : n번재 헤드 필드의 키 반환

 - getHeaderFieldInt (String name, int default) : int형으로 구문 분석된 필드의 값을 반환

 - getHeaderFielLong (String name, long default) : LONG형으로 구문 분석된 필드의 값을 반환

 - getHeaderFieldDate (String name, long default) : 날짜와 시간으로 구문 분석된 필드의 값을 반환

 - getDate () : 서버의 날짜 시간 값을 반환

 - getExpiration () : expires 필드 값을 반환

 - getContentEncoding () : 컨텐츠의 인코딩 헤더 필드의 값을 반환

 - getContentLength () : 컨텐츠 길이 필드의 값을 반환

 - getContentType () : 컨텐츠 타입 필드의 값을 반환

 - getLastModified () : last-modified 필드의 값을 반환
 ```
 
</br>

**5. 원하는 정보 담아보내기**   

> 연결에서 출력을 활성화를 해야 서버로 데이터를 보낼 수 있다  

```
 urlConnection.setDoOutput(true);
```

</br>

> Query String 형식으로 데이터를 담아보내기  

```
 String param = "query=안녕";

 DataOutputStream dataOutputStream = new DataOutputStream(urlConnection.getOutputStream());

 dataOutputStream.writeBytes(param);
 dataOutputStream.flush();
 dataOutputStream.close();

```

</br>

> Json형식으로 데이터를 담아보내기  

```
 JSONObject json = new JSONObject();

 json.put("Key", "Value");

 String param = json.toString(); 

 DataOutputStream dataOutputStream = new DataOutputStream(urlConnection.getOutputStream());

 dataOutputStream.writeBytes(param);
 dataOutputStream.flush();
 dataOutputStream.close();
```

</br>

**6. 전송된 데이터 읽기**  

> **HttpURLConnection**에서는 **getResponseCode()** 메서드를 통해 Http 상태코드를 읽어와 전송의 결과를 알고 그에 따라 대응이 가능하다.
> ex) 성공시 200 (HttpStatus.OK라는 통신 성공의 값)

</br>

> **InputStream** 생성 후 데이터 읽어오기

```
InputStream inputStream = urlConnection.getInputStream();
BufferedReader br = new BufferedReader(new InputStreamReader(inputStream, "UTF-8"));
```

</br>

> 데이터를 문자열로 변환  

```
 StringBuffer stringBuffer = new StringBuffer();
 String inputLine;
 
 while((inputLine = br.readLine()) != null) {
     stringBuffer.append(inputLine);
 }
 
 String result = stringBuffer.toString();
```  

</br>

> **getInputStream ()** 은 예외처리가 필요  
> - **IOException** : InputStream 생성시 I/O 오류가 발생한 경우
> - **SocketTimeOutException** : 데이터를 읽기 전 읽기 제한 시간이 만료되는 경우
> - **UnknownServiceException** : 프로토콜이 입력을 미지원시

</br>

**7. 연결 해제**  

> **InputStream** 또는 **OutputStream**에서 **close()** 메서드를 호출함으로써 **URLConnection**과 연결된 네트워크 리소스가 해제된다


