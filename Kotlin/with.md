```kt
import java.util.*
fun main(){
    val sc = Scanner(System.`in`)
    with(sc){
        val c = nextInt()
    }
    val a = sc.nextInt()
    val b = sc.nextInt()
   println(a/b)
}
```

 this = sc인데 this는 생략 가능   
 그래서 val c = nextInt()

- 조심해야할 것   
with(변수)인데 변수에 타입이 들어간다   
타입이 들어간다는 건 인스턴스도 들어감   
그래서 변수가 겹치면 변수 이름이 with를 사용한 클래스의 변수는 this@사용한클래스.변수 이렇게 해야한다   
with로 사용된 클래스의 변수는 그냥 불러와진다
