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
 <img width="100%" height="100%" alt="네이버_안녕검색화면" src="https://user-images.githubusercontent.com/67998815/153976659-0b7a0a13-e890-4deb-ab92-c340c30bded6.PNG">  
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
 - setDoOutput (boolean doOutput)
 - setIfModifiedSince (long time)
 - setAllowUserInteraction (boolean allow)
 - setDefaultAllowUserInteraction (boolean default)
 - setRequestProperty (String key, String value)
```   


#### - HttpURLConnection Method


< 작성중 >
