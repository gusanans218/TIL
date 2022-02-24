 # Array (배열)
-  같은 타입의 변수를 묶음으로 나타내는 것이다

 ###  list (Type)

- API값 빼고는 값 변경이 불가능하다.
- 그래서 list가 api 응답에 쓰이는 경우가 많다
- 컬렉션이라서 객체를 못 만든다.
  - List<obj>() 이렇게 객체를 만들어야하는데 불가하다

### arraylist (Type)

- 값 변경 가능
-
- arrayListOf는 listOf 처럼 미리 값을 넣을수가 있어요
  
### mutablelist (잘 안 쓴다)
 

 ### listOf (함수)

- listOf는 listOf<obj>() 에서() 안에 값을 미리 넣어두면 사용은 가능하다.


#### list랑 listOf의 차이는?
- list는 타입이고 listOf는 함수이다
  -  타입과 함수의 차이는?
     - 타입 = 클래스
     - 타입은 동작을 가지고 있는거고 함수는 동작을 실행하는 것이다



```kt
val arrayList = ArrayList<String>()
arrayList.add("one")
arrayList.add("two")


val arrayList = arrayListOf<String>("one", "two")


//두 코드는 같다
```

https://youjourney.github.io/archivers/ARRAYLIST



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