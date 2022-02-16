# URLConnection  
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
<img width="100%" height="100%" alt="네이버_안녕검색코드" src="https://user-images.githubusercontent.com/67998815/153979911-d485c682-2743-45b5-93c3-7e1be141e33e.PNG">

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


< 작성중 >
