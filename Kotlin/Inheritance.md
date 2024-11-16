## 클래스 상속
- **`open` 키워드**: 코틀린의 클래스는 기본적으로 `final`(상속 불가) 상태  
  상속하려면 클래스에 `open` 을 붙여야 함
  
```kotlin
open class Person(val name: String, val age: Int) // 상속 가능
class Student(name: String, age: Int, val id: Int) : Person(name, age) // 상속
```

## 생성자와 상속
슈퍼클래스 생성자 호출: 서브클래스는 반드시 슈퍼클래스의 생성자를 호출  
주 생성자는 : 슈퍼클래스 생성자(인수) 형태로 호출 
```kotlin
open class Person(val name: String, val age: Int) {
    constructor(name: String) : this(name, 0) // 보조 생성자
}

class Student(name: String, age: Int, val id: Int) : Person(name, age)
```

## 멤버 재정의 (override)
- 슈퍼클래스의 메서드나 프로퍼티를 재정의하려면   
    - 슈퍼클래스의 멤버에 open 키워드를 붙임.
    - 서브클래스에서 override 키워드를 사용.

```kotlin
open class Person(val name: String) {
    open fun introduce() {
        println("안녕하세요, $name 입니다.")
    }
}

class Student(name: String, val id: Int) : Person(name) {
    override fun introduce() {
        println("안녕하세요, $name 입니다. 학번은 $id 입니다.")
    }
}

fun main() {
    val person = Person("변승현")
    val student = Student("김길동", 20220117)
    person.introduce()  // "안녕하세요, 변승현 입니다."
    student.introduce() // "안녕하세요, 김길동 입니다. 학번은 20220117 입니다."
}
```
## 상속 제한
- final 키워드: 특정 멤버를 재정의하지 못하도록 제한
(코틀린의 모든 클래스와 멤버는 **기본적으로 final** 상태)

```kotlin
open class Person {
    open fun introduce() {
        println("안녕하세요!")
    }
}

class Student : Person() {
    final override fun introduce() { // Student에서 재정의 불가
        println("학생입니다.")
    }
}
```

## 다중 상속 불가
- 코틀린은 단일 상속만 허용   
- 다중 상속이 필요하면 인터페이스를 사용하여 구현

```kotlin
interface Driveable {
    fun drive()
}

interface Studyable {
    fun study()
}

class Student(name: String, age: Int, val id: Int) : Person(name, age), Driveable, Studyable {
    override fun drive() {
        println("운전합니다.")
    }

    override fun study() {
        println("공부합니다.")
    }
}
```

## super 키워드
서브클래스에서 슈퍼클래스의 멤버를 호출할 때 사용
```kotlin
open class Person(val name: String) {
    open fun introduce() {
        println("저는 $name 입니다.")
    }
}

class Student(name: String, val id: Int) : Person(name) {
    override fun introduce() {
        super.introduce() // 슈퍼클래스의 introduce 호출
        println("학번은 $id 입니다.")
    }
}
```