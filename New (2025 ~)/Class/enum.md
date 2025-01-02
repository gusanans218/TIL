# Enum Class

- 미리 정의된 상수들로 이뤄진 제한된 집합을 표현하는 특별한 클래스
- 정해진 상수들로 타입 안전하게 다룰수 있다
    - 대문자를 쓰는 이유 : 컴파일 시점 상수이기 때문이다

```kt
enum class WeekDay {
    MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUMDAY
}
```

- 모든 이넘 값에는 ordinal과 name이라는 한 쌍의 프로퍼티가 들어있다
     - **ordinal은 이넘 값의 순서에 따른 인덱스**
    - **name은 이넘 값의 이름**이다


```kt
enum class Direction {
    NORTH, SOUTH, WEST, EAST
}

fun main(){
    println(Direction.WEST.name)    // WEST
    println(Direction.WEST.ordinal) // 2
}
```