# `lateinit`와 `by lazy`의 사용법과 차이점

## `lateinit`
- **선언 시 타입만 지정하고 초기화는 나중에 할 수 있음**  
  `lateinit`은 초기값을 나중에 할당할 수 있게 해줌. 꼭 나중에 **초기화**를 해줘야 하고, 그렇지 않으면 사용 시 **UninitializedPropertyAccessException**이 발생함.

- **Nullable 타입에는 사용 불가**  
  `lateinit`은 무조건 **Non-null** 타입이어야 해서, `null`이 될 수 없는 변수를 초기화 전에 설정할 때 유용함.

  ```kotlin
  lateinit var userName: String
  
  fun initUser() {
      userName = "Alice" // 나중에 초기화
  }
  
  fun printUser() {
      println(userName) // 초기화된 후에만 접근
  }

- **주로 Android에서 View Binding과 함께 사용**  
  Android 개발에서는 `lateinit`으로 View를 나중에 초기화하는 경우가 많음. 예를 들어, `Activity`나 `Fragment`의 `onCreate`나 `onViewCreated`에서 뷰를 초기화할 때 사용함.

## `by lazy`
- **읽기 전용 변수(val)에서 사용**  
  `by lazy`는 `val`과 함께 쓰여 **읽기 전용(read-only)** 값을 다룰 때 유용함. 값을 초기화한 후 다시 변경할 수 없기 때문에 불변성을 유지할 수 있음.

- **변수에 접근할 때만 초기화**  
  선언할 때는 초기화되지 않고, **처음 사용되는 순간** 초기화가 진행됨. 그래서 **메모리 낭비를 줄이고, 필요한 시점에만 초기화**하게 해줌.

  ```kotlin
  val greeting: String by lazy { "Hello, Lazy!" } // 처음 접근 시 초기화됨
  
  fun printGreeting() {
      println(greeting) // 여기서 초기화됨
  }

- 무거운 연산을 처리할 때 유용 ( 데이터를 불러오거나 복잡한 계산이 필요한 경우에만 초기화하게 할 때 사용하면 좋음)