# RxJava
- 비동기 프로그래밍과 함수형 프로그래밍 기법을 함께 활용하는 것이다.

- 비동기 흐름을 구성해주는 연산자 제공
- 콜백을 사용하지 않는 방향으로 설계


## Observable
- 데이터 흐름에 맞게 Consumer에게 알림을 보내는 class다.
- Observavle을 구독하는 Observer가 존재함   
Observable이 순차적으로 발행하는 데이터에 대해 반응한다.    
그리고 상태 변화가 있을 떄마다 메서드를 호출하여 객체가 직접 목록의 각 옵저버에게 변화를 알려준다. (LifeCycle 존재 하지 않음)

### onNext()
-  Observable에서 Observer까지 한 번에 하나씩 데이터를 발행한다.

### onComplete()
-  데이터 발행이 끝났음을 알리는 완료 이벤트를 Observer에 전달해 onNext()를 더 호출하지 않음을 나타낸다.

### onError() 
- 오류가 발생했음을 Observer에 전달한다.


## subscribe()
Observable은 subscribe를 해야 데이터가 발행된다.   
just()만 호출하면 데이터 발행이 없다.
- Observable을 subscribe -> 수신한 데이터를 원하는 방식으로 사용.

subcribe는 onSuccess와 onError를 가지고 있고
onSuccess 데이터 반환을 성공할때 호출.   
onError 데이터를 가져오는 도중 오류가 발생하면 호출을 한다.   
onError 보통 서버의 500 에러가 보통 여기로 나온다.   
다만 감독자가 필요하다. 따라서 addTo(CompositeDisposable)을 통해 감독자에게 등록해준다

```kt
fun getInviteInformation(){
        api.getInviteCode()
            .subscribeOn(Schedulers.io())
            .observeOn(AndroidSchedulers.mainThread())
            .subscribe({
                _inviteCode.value = it.code
                _inviteCount.value = it.inviteCount
                link = it
                _invitees.value = it.invitees
            }, {
                it.printStackTrace()
            }).addTo(compositeDisposable)
    }//rxjava 예제
```

## just()
아이템을 그대로 발행하는 Observavle을 생성.   
just()에 넣은 아이템을 차례로 발행, 한 개의 아이템을 넣을 수도 있고, 타입이 같은 여러 아이템을 넣을 수도 있다.
```kt
Observable<String> source = Observable.just("Hello", "World");
source.subscribe(System.out::println());
//just 예제

``` 



CompositeDisposable() -> 관리 감독 같은 기능