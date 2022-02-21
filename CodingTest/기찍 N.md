## 자연수 N이 주어졌을 때, N부터 1까지 한 줄에 하나씩 출력하는 프로그램을 작성하시오.

```kt
import java.util.Scanner
fun main(){
   val sc  = Scanner(System.`in`)
    var rep = sc.nextInt()


    for(i in rep downTo 1)
    {
       println(i)
    }

}
```

- downTo 함수를 썼다.   
이 함수를 쓰면 쉽게 코드를 짤 수 있다~~