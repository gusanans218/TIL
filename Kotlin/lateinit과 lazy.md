# lateinit과 lazy

## lateinit
 ```kt
 lateinit var x : String
x = "Initialized"
println(x)
```
- var에 String 타입
- x가 null이 될 수 없다.
- 사용 전에 초기화 단계를 거쳐야 한다.

## by lazy
```kt
lateinit var inputValue : String
val x : Int by lazy { inputValue.length }
inputValue = "Initialized!"
println(x)
```
- val과 사용 시에 어떤 값이 들어가는지 정함

## lateinit과 by lazy의 차이
- lateinit은 var, lazy는 val
- 초기화 이후에 갑이 변할 수 있는 변수는 lateinit, read-only로 쓰이는 변수에는 by lazy