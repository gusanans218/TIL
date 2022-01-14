# 프로퍼티와 Getter/Setter

```kt
class Person
{
    var age: Int = 0
    get()
    {
        return field
    }
    set(value)
    {
        field = if(value >=0)value else 0
        //field에 value가 0이상이면 저장
        //음수이면 0으로 그냥 저장
    }
}


fun main(args:Array<String>)
{
    val person = Person()
    person.age =-30
    println(person.age)
}


//
```

#### Property
- Field : 실제도 데이터가 저장되는 공간
- Getter : 저장된 값을 읽으려고 할 때 호출되는 함수
- Setter : 값을 저장하려고 할 때 호출되는 함수
- val에는 Getter만 존재
    - 초기 값이 주어지면 값을 변경(Set)할 수가 없기 때문이다.
    - val에는 초기값 무조건 있어야됨

```kt
class Rectangle {
    var width = 10
        set(value) {
            field = value / 2
        }
    var height = 10
        set(value) {
            field = value / 2
        }
    var area: Int = 0
        get() = width * height
}

// 위의 객체는 이렇게 사용할 수 있습니다.
fun main(args: Array<String>) {
    val rect = Rectangle()
    println("width: ${rect.width}")
    println("height: ${rect.height}")
    println("area: ${rect.area}")

    rect.width = 40
    rect.height = 40
    println("width: ${rect.width}")
    println("height: ${rect.height}")
    println("area: ${rect.area}")
}
//예시 코드

//width: 10
//height: 10
//area: 100
//width: 20
//height: 20
//area: 400
```