# list

1. Immutable 리스트 정렬
- 데이터 변경이 안되는 리스트를 정렬할 때 사용 = sorted()

```kt
fun main(args:Array<String>){
    val list = listOf(10,100,50,2,77,4)

    val sorted = list.sorted()
    println("sorted: $sorted")
}

//Output
sorted: [2,4,10,50,77,100]
```

2. Mutable 리스트 정렬
- 데이터 변경이 가능한 리스트의 요소들을 정렬한다. = sort()

```kt
fun main(args:Array<String>)
{
    val list = mutableListOf(10,100,50,2,77,4)
    list.sort()
    println("sorted: $list")
}

//Output
sorted : [2,4,10,50,77,100]
```

3. 역순으로 정렬
- reversed() x  