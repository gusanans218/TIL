# Generic

### 제네릭 인터페이스 (GenericInterface<T>)

- 인터페이스에서 타입 파라미터 `T`를 사용하여 다양한 타입을 지원할 수 있게 함.
- `T`에 원하는 타입을 지정하면, 그 타입만 허용하는 인터페이스로 동작함.

### 인터페이스 구현 시 타입 지정

- `GenericInterface<String>`처럼 특정 타입으로 구현하면 `String`만 반환함.
- `GenericInterface<Int>`로 구현 시 `Int`만 반환하게 됨.
- 타입별로 분리된 구현을 가능하게 하여 타입 안전성을 확보함.

### 제네릭 타입 리스트 (ArrayList<T>) 사용

- `ArrayList<T>`와 같은 제네릭 컬렉션은 `T` 타입을 지정하여 해당 타입만 저장 가능하게 함.
- 예를 들어, `ArrayList<Int>`는 `Int` 타입만 추가할 수 있어, 잘못된 타입 입력을 방지함.

### 타입 안전성

- 제네릭을 사용하면 잘못된 타입을 넣는 것을 컴파일러가 막아줌.
- 덕분에 런타임 오류를 줄이고 코드 안정성을 높임.


## 관련 코드

```kt
class GenericExample {
    // GenericInterface<String> 타입으로 구현한 객체 interfaceExample
    val interfaceExample = object : GenericInterface<String>{
        override val genericInterfaceValue: String
            get() = "genericInterfaceValue" // getter를 통해 "genericInterfaceValue"라는 문자열을 반환함.

        override fun genericInterfaceFunction() : String {
            return "genericInterfaceFunction" // genericInterfaceFunction() 호출 시 "genericInterfaceFunction" 반환.
        }
    }

    // GenericInterface<Int> 타입으로 구현한 객체 intGenericExample
    val intGenericExample = object : GenericInterface<Int>{
        override val genericInterfaceValue: Int
            get() = 1 // getter를 통해 1 반환.

        //setter : 값을 설정하기 위한 함수지만, val로 선언되어 있어 setter는 자동 생성되지 않음.
        //getter : genericInterfaceValue 호출 시 값을 반환해주는 역할.
        
        override fun genericInterfaceFunction(): Int {
            return 2 // genericInterfaceFunction() 호출 시 2 반환.
        }
    }

    // Int 타입의 요소만 저장 가능한 ArrayList 생성
    val arrayList = ArrayList<Int>() // ArrayList<Int>로 타입을 Int로 설정하여 숫자만 저장 가능.

    fun function(){
        intGenericExample.genericInterfaceValue // genericInterfaceValue가 호출되면 Int 값인 1을 반환.
        arrayList.add(1) // ArrayList<Int>이기 때문에 Int 값만 추가할 수 있음.
        // String으로 바꾸면 add("skdjfls")가 가능함.
    }
}

// 제네릭 인터페이스로, T 타입을 파라미터로 받음.
// T는 인터페이스를 구현할 때 지정하며, Int, String 등의 타입이 들어갈 수 있음.
interface GenericInterface<T>{
    val genericInterfaceValue : T // T 타입의 값으로 지정
    fun genericInterfaceFunction() : T // T 타입의 값을 반환하는 함수
}
```
