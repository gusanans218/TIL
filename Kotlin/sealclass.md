```kt
sealed class SealType{
    object Type1 : SealType()
    object Type2 : SealType()
    object Type3 : SealType()
}

object Type4 : SealType()//같은 파일이라 가능
```