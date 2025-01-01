## SerializedName

- SerializedName는 코틀린의 필드 네임과 JSON 키 이름이 다를 경우 이를 매핑해주는 역할을 한다

왜냐하면 JSON - 스네이크 표기법 사용
       Kotlin - 카멜 표기법 사용

그래서 @SerializedName을 사용해 매핑해줘야한다

```kt
data class User(
    @SerializedName("user_name") val userName: String,
    @SerializedName("user_age") val userAge: Int
)
```

- Kotlin 필드 이름과 JSON 키 이름이 동일한 경우에는 굳이 사용하지 않아도 된다.


