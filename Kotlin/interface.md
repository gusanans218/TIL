# interface
- 클래스의 형태를 정해주는 틀 역할
-  극단적으로 동일한 목적 하에 동일한 기능을 보장하게 하기 위함이다.

```kt
interface ExchangeRepository {
    suspend fun getExchangeInfo(): ExchangeInfoModel?
```