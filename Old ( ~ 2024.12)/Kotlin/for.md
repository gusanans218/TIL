# for문

```kt
for(변수 이름 : 타입 in 표현식)
{

}
```

```kt
fun main(args:Array<String>)
{
    for(i : Int in 1..10)
        print("$i") //12345678910
    println()

    for(i:Int in 1..10)
    {
        if(i>5)
            break

            print("$i") //12345
    }
}
```

```kt
for(i in 1..10) //1부터 10사이에 있는 i에 대해
```

```kt
//원래 코드
for(i : Int in 1..10)
    print("$i")

//컴파일된 코드
for(i = 1; i<=10 ++i)
    println("$i);
```