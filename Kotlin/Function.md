# Function 



```kotlin
fun main() {
    print(plus(1, 2))   //3
    print(minus(b = 3))       //2
    printTest()               //TEST
}

fun plus(a : Int, b : Int) : Int{
    return a + b
}

fun minus(a : Int = 1, b : Int) : Int{
    return b - a
}

fun printTest(){
    print("TEST")
}
```

함수는 {} 안에 있는 코드들을 묶어서 다른 곳에서 편리하게 끌어다가 쓸 수 있는 것이다.



https://github.com/swj0704/AndroidGuide/blob/main/KotlinExample/src/main/java/com/wonjoonshin/kotlinexample/FunctionExample.kt

