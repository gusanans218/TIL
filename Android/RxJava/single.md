# Single

- Observable과는 다르게 단 하나의 아이템만을 발행한다.

```java
Single.just("Hello World")
    .subscribe(System.out::println);
```

Single<데이터클래스> 이걸로 retrofit response 받고

Call<데이터> -> Single<데이터>

위에서 subscribeon observeon 해주고 subscribe에 중괄호 두개 붙이고 앞은 onSuccess인데 Call일때 onResponse랑 비슷하다 
