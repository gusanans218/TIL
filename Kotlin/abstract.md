# abstract

- 반드시 override 해줘야한다.
- 상속을 하려면 open을 선언해야한다.
    아무 선언이 없으면 final class랑 같기 때문이다.

```kt
abstract class Person{
    open fun eat(){}
    abstract fun sleep()
}

class Student : Person(){
    override fun eat(){
        super.eat()
    }

    override fun sleep(){}

    fun study(){}
}