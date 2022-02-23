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
- reversed() : Immutable리스트에서 사용. 역순으로 변경된 리스트를 생성한다.
- reverse() : Mutable 리스트에서 사용. 리스트 자신의 요소 순서를 반대로 변경

```kt
fun main(args:Array<String>)
{
    //1. immutable list
    val list = listOf(10,100,50,2,77,4)

    //2. mutable list
    val list2 = mutableListOf(10,100,50,2,77,4)
    list2.sort()
    list2.reverse()
    println("sorted: $list2")
}

//Output
sorted : [100, 77, 50, 10, 4, 2]
sorted : [100, 77, 50, 10, 4, 2]
```

4. sortedWith(), sortWith()

- sortedWith() : Immutable list에서 사용
- sortWith() : Mutable list에서 사용