
```kt
class EnumClassExample{
    enum class Type(number : Int){
        FRIEND(1),
        REALFRIEND(2)
    }

    var t : Type = Type.FRIEND 

    fun checkType(t : Type) : Boolean{
        return t == Type.FRIEND //true가 나온다.
    }
}
```




