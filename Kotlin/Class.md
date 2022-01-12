# Class (클래스)
 모양이 같은 객체를 대량 생산할 수 있다. <hr>

 ```kotlin
 val person = object
 {
     val name : String = "홍길동"
     val age : Int = 36
 }

 val person2 = object
 {
     val name : String = "변승현"
     val age : Int = 19
 }
 //일일이 객체 만들기에는 번거로움
// => 클래스로 해결
```

```kotlin
class Person
{
    var name : String = ""
    var age : Int = 0
    //var val 상관 없다
}

fun main(args:Array<String>)
{
    val person : Person //선언만 해줌
    person = Person() //클래스 부르는 부분 
    //그래서 두줄은 같이 움직여야 한다


    val person = Person()
    //이렇게 한줄로 줄여서 쓸 수도 있다.
    //초기화를 무조건 시켜야한다
    //안 그러면 'Variable 'person' must be initalized' 오류 남

    person.name = "홍길동"
    person.age = 36

    val person2 : Person
    person.name = "변승현"
    person.age = 19
}
```

### 클래스 선언하는 법
```kotlin
class 클래스 이름
{
    프로퍼티
}
```

- 클래스에서 생성된 객체   
  = 인스턴스


#### 생성자

- 클래스를 이용해서 객체를 찍어내기 위한 방법
- 하나의 클래스에는 반드시 하나 이상의 생성자가 존재해야 한다.


```kotlin
(name:String)//primary

constructor(name : String, height : Int) : this(name)//second constructor 근데 사용 잘 안 함;;
// primary에 name 있는거를 second에 name을 무조건 끌어다 써야한다
```

### class의 instance 생성하기
```java
Person person = new Person();
//Java
```

```kotlin
val person = Person()
```



