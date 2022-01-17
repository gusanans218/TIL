# 업캐스팅 (Upcasting)

  #### 캐스팅 또는 형변환이란, 특정 타입을 다른 타입으로 변환하는 것
  ### 서브클래스(Student)의 인스턴스를 슈퍼클래스(Person) 타입으로 가리킬 수 있다.

  ```kt
  open class Person(val name:String, val age : Int)

class Student(name:String age:Int, val id:Int):Person(name,age)

fun main(args:Array<String>)
{
    val person:Person = Student("John",32,20220117)
}
```

