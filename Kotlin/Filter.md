## Filter

### filter
- 컬렉션의 각 요소를 검사하여 조건을 만족하는 요소들만을 필터링

```kt
val numbers = listOf(1,2,3,4,5,6)
val evenNumbers = numbers.filter { it % 2 == 0}
println(evenNumbers) // 2,4,6
```

```kt
val words = listOf("apple","banana","cherry","kiwi")
val longWords = words.filter {it.length > 5 }
println(longWords) // banana, cherry
```

### filterNot
- 주어진 조건을 만족하지 않는 요소들만을 필터링
```kt
val numbers = listOf(1,2,3,4,5,6)
val oddNumbers = numbers.filterNot {it % 2 == 0 }
println(oddNumbers) // 1,3,5
```

### filterNotNull
- null이 아닌 요소들만을 필터링
```kt
val mixedList = listOf(1,2,null,4,null,6)
val notNullList = mixedList.filterNotNull()
println(notNullList) // 1,2,4,6
```

### filterIsInstance
- 주어진 클래스 타입의 인스턴스들만을 필터링
```kt
val mixedList: List<Any?> = listOf(1, "two","3.0,"four, 5)
val strings = mixedList.filterIsInstance<String>()
println(strings) // two, four
```

### filterIndexed
- 인덱스를 함께 사용하여 요소를 필터링
```kt
val numbers = listOf(1,2,3,4,5,6)
val evenIndexedNumbers = numbers.filterIndexed { index, _ -> index % 2 == 0 }
println(evenIndexedNumbers) // 1,3,5
```