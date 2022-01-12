#  Object (객체)
  서로 관련 있는 변수를 하나로 묶는 법<hr>
---
  


```kotlin
val personName = "홍길동"
val personAge = 36
```
=> 이렇게 하면 코드 중복의 문제 발생

### object 사용하면 해결

```kotlin
val person = object
{
    val name : String = "홍길동"
    val age : Int = 36
}
    println(person.name)
    println(person.age)
    //이렇게 객체를 사용할 수 있다.
```

name, age처럼 object에 포함된 변수들은 *Property*라고 한다. 
* 반드시 선언과 동시에 초기화
  
  ```kotlin
  fun main(ages:Array<String>)
  {
    val person = object
    {
      val name : String = "홍길동"
      val age : Int = 36
    }
    println(person.name)
    println(person.age)
  }
  //예시 코드
