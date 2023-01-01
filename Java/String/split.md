## split 

> 문자열을 구분, 자르기 하는 JAVA의 String 메서드 

</br>

## split 사용방법

#### split(String regex) </br>

> regex(정규표현식)을 기준으로 문자열을 나눌 때 사용한다.

```
String str = "abc def ghi";
String[] splitString = str.split(" ");

for(String s : splitString) {
    System.out.println(s);
}
```

> <실행 결과> </br>
> abc </br>
> def </br>
> ghi </br>

 </br>

#### split(String regex, int limit)  </br>

> regex(정규표현식)을 기준으로 문자열을 나눌 때, 배열의 크기는 limit를 넘지않는다.

```
String str = "a b c d e f g h i";
String[] splitString = str.split(" ", 5);

for(String s : splitString) {
    System.out.println(s);
}
```

</br>

> <실행 결과> </br>
> a </br>
> b </br>
> c </br>
> d </br>
> e f g h i </br>
> 
> 공백(" ")으로 잘 나눠지다가 limit 5에 도달하자 더이상 나누지 않고 마지막 배열에 나머지 문자열이 다 들어간다.  

 </br>


#### split() 마지막 공백 포함하여 처리하기  </br>

```
String str = "a,b,c,,d,";
String[] splitString = str.split(",", -1);

for(String s : splitString) {
    System.out.println("split후 : " + s);
}
```

> <실행 결과> </br>
> split후 : a </br>
> split후 : b </br>
> split후 : c </br>
> split후 :  </br>
> split후 : d </br>
> split후 :  </br>

 </br>
 
 > limit에 음수값을 주면 기존에는 무시되었던 공백이 처리되어 표현된다.
