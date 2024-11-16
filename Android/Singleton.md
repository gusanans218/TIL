# Singleton (싱글턴)

- 코틀린 사용해서 Singleton 구현
```kt
/** object 키워드로 싱글톤 구현하기 */
object DataRepository {}

//코틀린에서 사용
>>> val dataRepository = DataRepository

//자바에서 사용
>>> DataRepository dataRepository = DataRepository.INSTANCE;
```

object가 싱글톤 선언이다.   
코틀린에서는 객체명만을 사용해서 선언,
자바에서는 INSTANCE 필드를 호출해서 선언한다.