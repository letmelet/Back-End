#  Stream 이란?  
</br>

> **Stream API**는 **데이터의 흐름**으로 배열, 컬렉션등을 원하는대로 가공하여 결과를 얻을수 있으며 </br></br>
> JAVA8부터 지원되는 람다식, 함수형 인터페이스등과 사용하여 
> **객체지향형 언어인 JAVA를 함수형으로 프로그래밍할 수 있게 해주는 API**

</br>

## Stream API 특징  
</br>

> - 원본의 데이터를 변경하지않음
> - 내부 반복을 통해 작업을 수행
> - 재사용이 안되는 일회성 
> - ParallelStream() 메서드를 통한 손쉬운 병렬 처리를 지원

</br>


## Stream API 연산  
</br>

> #### 1. 생성하기 </br>
>   &nbsp;  Stream 객체를 생성하는 단계. </br>
>        컬렉션, 배열, 람다식, 파일 등등에서 생성 가능하다. </br>
> #### 2. 가공하기 </br>
>    &nbsp; 생성된 Stream을 원하는대로 가공하는 단계. </br>
>        필터링, 변환, 정렬 등등의 가공방법이 있다. </br>
> #### 3. 결과만들기 </br>
>    &nbsp; 가공한 Stream을 원하는 결과로 나타내는 단계. </br>
>        출력, 소모, 연산, 수집 등등의 결과 처리방법이 있다.

</br>

## Stream 생성하기 </br>

- 컬렉션 Stream 생성 </br>

```
Stream<Integer> stream = new ArrayList<Integer>().stream();
```

- 배열 Stream 생성 </br>

```
Integer[] array = new Integer[]{1,2,3,4};
       
Stream<Integer> stream = Arrays.stream(array);
```


- 람다식 Stream 생성 </br>

```
Stream<Integer> stream = Stream.iterate(1,x -> x+1);
```


- 연속된 정수 Stream 생성 </br>

```
IntStream stream1 = IntStream.range(0,10); 
 // range : 시작 정수부터 마지막 정수는 포함하지 않는 범위 (0 ~ 9)
```

```
IntStream stream2 = IntStream.rangeClosed(0,10);
 // rangeClosed : 시작 정수부터 마지막 정수까지 포함하는 범위 (0 ~ 10)
```


- 빈 Stream 생성 </br>


```
Stream<Object> stream = Stream.empty();
```


## Stream 가공하기 </br>

- 필터링       </br>

```
IntStream stream1 = IntStream.range(0,10);
stream1.filter(n-> n%2 = 0);
 // 0~9 까지의 정수중 짝수만 남게 필터링
```


- 변환  

```
Stream<String> stream = Stream.of("Hello", "java", "spring", "backEnD");
stream.map(s -> s.toUpperCase());
  // 스트림의 문자들을 대문자로 변환
```

- 제한  

```
IntStream stream1 = IntStream.range(0,10);

stream1.limit(3).forEach(n -> System.out.print(n + " ");
  // 스트림의 첫 번째 요소부터 limit 개수 만큼의 요소만으로 이루어진 스트림 반환
  // 실행결과 : 0 1 2
```  
  
```
IntStream stream2 = IntStream.range(0,10);

stream2.skip(3).forEach(n -> System.out.print(n + " ");
  // 스트림의 첫 번째 요소부터 skip 개수 만큼 제외한 나머지 요소만으로 이루어진 스트림 반환
  // 실행결과 : 3 4 5 6 7 8 9
```

- 정렬   

```
Stream<String> stream = Stream.of("Hello", "java", "spring", "backEnD");
stream.sorted().forEach(s -> System.out.print(s + " ");
  // 오름차순으로 정렬.
  // 실행결과 : backEnD Hello java spring
```

- 특정 연산 수행                     

```
IntStream stream = IntStream.of(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

stream.peek(s -> System.out.println("Original Stream : " + s))
      .skip(2)
      .forEach(n -> System.out.println(n));
```

```
// 실행결과

Original Stream : 1
Original Stream : 2
Original Stream : 3
3
Original Stream : 4
4
Original Stream : 5
5
Original Stream : 6
6
Original Stream : 7
7
Original Stream : 8
8
Original Stream : 9
9
Original Stream : 10
10

```

## Stream 결과만들기 </br>

- 출력      

- 연산

- 수집

- 검사  

- 통계    
