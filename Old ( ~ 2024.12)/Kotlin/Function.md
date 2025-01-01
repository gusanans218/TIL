# Function 



```kotlin
fun main() {
    print(plus(1, 2))   //3
    print(minus(b = 3))       //2
    printTest()               //TEST
}//fun 키워드 붙으면 메서드

fun plus(a : Int, b : Int) : Int{
    return a + b
    //return의 기능
    //값을 넘겨주는 기능
    //함수를 끝내는 기능
}

fun minus(a : Int = 1, b : Int) : Int{
    return b - a
    // :Int에 return 타입 들어감
    // a,b가 Int니까 :Int가 되는 것
    //따라서 메서드에서는 
    //Person객체를 리턴하기 때문에
    //:Person 으로 리턴하는 것과 타입을 맞춰줘야 한다
}

fun printTest(){
    print("TEST")
}
//매개변수는 필수가 아니다
```

함수는 {} 안에 있는 코드들을 묶어서 다른 곳에서 편리하게 끌어다가 쓸 수 있는 것이다.



https://github.com/swj0704/AndroidGuide/blob/main/KotlinExample/src/main/java/com/wonjoonshin/kotlinexample/FunctionExample.kt

