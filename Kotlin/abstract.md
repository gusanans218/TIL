# abstract (추상 클래스)


`abstract` 키워드는 클래스나 메서드가 반드시 구현이 필요하다는 의미에서 **추상적**임을 나타냄


- **인스턴스화 불가**: 직접 객체 생성이 불가능하며, 하위 클래스에서만 인스턴스화 가능.   

- **open 키워드 불필요**: `abstract` 함수는 자동으로 `open`이 적용되어 반드시 `override` 필요.
- **구현된 메서드 포함 가능**: 추상 메서드뿐 아니라 구현된 메서드도 가질 수 있음.
- **프로퍼티와 초기화 가능**: 생성자와 초기화 블록을 통해 상태 관리 및 초기화 가능.
- **인터페이스와 차이**: 단일 상속만 가능하고 상태 관리에 유리, 인터페이스는 다중 구현 가능하지만 상태 관리 불가.

```kt

abstract class AbstractClass(val t: Int) {      // 불완전한 클래스
    abstract val a: Int                         // 추상 프로퍼티
    abstract fun onClick()                      // 추상 메서드
    fun function(a: Int) {                      // 구현된 메서드
        print(a)
    }

    val b = 1
    init {
        println("AbstractClass가 t = $t 값으로 초기화되었습니다")
    }
}

class ConcreteClass(t: Int, override val a: Int) : AbstractClass(t) {
    override fun onClick() {
        println("ConcreteClass의 onClick이 호출되었습니다. a = $a")
    }
}

fun main() {
    val instance = ConcreteClass(10, 5)
    instance.onClick()
    instance.function(20)
}

// 출력 결과
AbstractClass가 t = 10 값으로 초기화되었습니다
ConcreteClass의 onClick이 호출되었습니다. a = 5
20

```


