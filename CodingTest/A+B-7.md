```kt
import java.util.Scanner
fun main(){
   val sc  = Scanner(System.`in`)
    var rep = sc.nextInt()


    for(i in 1.. rep)
    {
        var a = sc.nextInt()
        var b = sc.nextInt()
        println("Case #$i: "  +(a+b))
    }

}
```

- 앞에 문자열이 있고 그 뒤에 +가 오면 a랑 b가 자동으로 문자열로 바뀌어 더하기 계산이 되지 않는다  
 그래서 먼저 괄호를 써서 계산을 해주어야한다.



