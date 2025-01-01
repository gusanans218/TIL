# Room

- 스마트폰 내장 DB에 데이터를 저장하기 위해 사용하는 라이브러리다.

### Room과 SQLite의 차이점은?
- Room은 LiveData와 RxJava를 위한 Observation으로 생성하여 동작할 수 있지만 SQLite는 그렇지 않다.
- SQL쿼리를 수동으로 업데이트 해야하지만, Room은 그렇지 않다.

## Room의 구성요소
- Database
    - 앱이 영구 저장되는 데이터와 기본 연결을 위한 주 액세스 지점
```kt
@Database(
    entities = [LoginEntity::class],
    version = 1,
    exportSchema = false
)
```



- Entity
    - 데이터베이스 안의 테이블을 클래스로 나타낸 것
        - 하나 이상의 기본키를 설정해야함. (PrimaryKey)
    ```kt
    @Entity
    data class LoginEntity(
    val username: String,
    val password: String
    ) {
    @PrimaryKey(autoGenerate = true) var id: Int = 0
    }
   ```



- Dao
    - 데이터베이스에 접근하는데 사용되는 메소드들을 포함한다. (select, insert, delete 등)
    ```kt
    @Dao
    interface LoginDao {

    @Query("Select * From LoginEntity")
    fun getLogin() : LoginEntity

    @Query("DELETE From LoginEntity")
    fun deleteLogin()

    @Insert
    fun insetLogin(loginEntity: LoginEntity)

    }
    ```