# 다형성의 활용


```kt
 open class AAA
 {
     open fun hello() = println("AAA입니다")
 }
 class BBB:AAA()
 {
     override fun hello() = println("BBB입니다")
 }

 fun main(args:Array<String>)
 {
     val one = AAA()
     val two = BBB()
     val three : AAA = two

     one.hello()
     two.hello()
     three.hello()
    
 }

 //l