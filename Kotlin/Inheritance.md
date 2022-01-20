# 상속 (Inheritance)

```kt
open class Person(val name:String, val age : Int)
//클래스는 기본적으로 상속이 막혀있어서 open이라는 키워드를 붙여주어야 한다.


class Student(name:String age:Int, val id:Int):Person(name,age)

fun main(args:Array<String>)
{
    val person = Person("변승현",19)
    val student = Student("김길동",23,20220117)
}
```

- 슈퍼클래스 : 상속의 대상이 되는 클래스 (Person)
- 서브클래스 : 상속하여 확장된 클래스 (Student)
- class 클래스 이름 : 슈퍼클래스 생성자 (인수)

#### 상속은 하나의 클래스만 할 수 있다.