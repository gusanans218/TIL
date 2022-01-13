# init 블록 나누어 쓰기

```kt
class Size(width:Int, height:Int)
{
    val width = width //1
    val height = Int

    init
    {
        this.height = height //2
    }

    val area:Int

    init
    {
        area = width * height //3
    }
}

fun main(args:Array<String>)
{
    val size = Size(10,50)
    println(size.area)
}
```