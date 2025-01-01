```kt
import java.util.*

fun main(){
    val sc = Scanner(System.`in`)
    val x = sc.nextInt()
    val y = sc.nextInt()
    
    for(i in 0 until x)
    {
        val z = sc.nextInt()
        if(y>z)
        {
            print(z.toString() + " ")
        }
    }
}
```