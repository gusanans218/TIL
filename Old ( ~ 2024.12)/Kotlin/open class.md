# open class 
- 클래스의 상속을 허용하려면 해당 클래스 앞에 open 변경자를 붙여야한다.
- 오버라이드를 허용하고 싶은 메서드나 프로퍼티의 앞에도 open 변경자를 붙여야한다.
```kt
open class Car {

    // 이 메서드는 하위 클래스에서 override 불가능
    fun getNumberOfTires(): Int {
        return 4
    }
    
    // 하위 클래스에서 override 가능
    open fun hasSunRoof() :Boolean {
        return false
    }
}

// open 클래스는 상속이 가능하다!
class Benz() : Car() {

    // getNumberOfTires 메서드는 override 불가능
    // hasSunRoof 메서드는 open변경자가 붙어서 override 가능
    override fun hasSunRoof(): Boolean {
        return true
    }
}
```

### open class : 다른 클래스에서 상속 가능
### open method : 해당 메서드를 하위 클래스에서 override 가능