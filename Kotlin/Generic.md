```kt
class GenericExample {
    val interfaceExample = object : GenericInterface<String>{
        override val genericInterfaceValue: String
            get() = "genericInterfaceValue"

        override fun genericInterfaceFunction() : String {
            return "genericInterfaceFunction"
        }

    }

    val intGenericExample = object : GenericInterface<Int>{
        override val genericInterfaceValue: Int
            get() = 1
        //setter : 값을 세팅
        //getter : 값을 반환? 불러오기?

        override fun genericInterfaceFunction(): Int {
            return 2
        }

    }

    val arrayList = ArrayList<Int>() //int로 선언된거다

    fun function(){
        intGenericExample.genericInterfaceValue
        arrayList.add(1) //int가 선언되어 있어서 숫자만 들어가진다.
        //String으로 바뀌면 add("skdjfls")가능.
    }
}

interface GenericInterface<T>{ // T에 Int나 String같은 타입이나 심지어 클래스 이름도 들어갈 수 있다.
    val genericInterfaceValue : T
    fun genericInterfaceFunction() : T
}
```
