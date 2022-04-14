# Single

- Observable과는 다르게 단 하나의 아이템만을 발행한다.

```java
Single.just("Hello World")
    .subscribe(System.out::println);
```

Single<데이터클래스> 이걸로 retrofit response 받고

Call<데이터> -> Single<데이터>

위에서 subscribeon observeon 해주고 subscribe에 중괄호 두개 붙이고 앞은 onSuccess인데 Call일때 onResponse랑 비슷하다 

### Koin의 Single?
- Singleton 객체를 생성
- 앱 전체적으로 보면 get이나 inject를 사용해서 앱 전체에서 쓸 수 있다.
- 하나의 객체를 사용하기 때문에 다른 Activity의 활동이 또 다른 Activity에서 영향을 받을 수 있다.
- A에서 바꾸면 B에서 바꾼 상태로 나타남 -> A 바꾸면 B도 바뀜
