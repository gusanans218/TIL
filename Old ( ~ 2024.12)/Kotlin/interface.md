# interface
- 클래스의 형태를 정해주는 틀 역할
-  극단적으로 동일한 목적 하에 동일한 기능을 보장하게 하기 위함이다.

```kt
interface ExchangeRepository {
    suspend fun getExchangeInfo(): ExchangeInfoModel?
```

```kt
class InterfaceExample {
}

fun main(){
    val viewClick = ViewClick(2, 3)
    println(viewClick.changeSize())
}

interface OnClickListener{
    val clickValue : Int
    var clickValue2 : Int

    fun onClick()

    //인터페이스를 사용하는 이유
    //비슷한 기능을 갖고 있는 클래스들의
    //형태를 통일 시키기 위해서

    // 한 클래스에서 여러 interface를 상속받을 수 있다 *****
}```

```kt
interface OnChangeListener{
    fun onChange()
}

class ViewClick(override val clickValue: Int /* 필드도 오버라이드 가능 */, override var clickValue2: Int) : OnClickListener, OnChangeListener{
    fun changeSize() : Int{
        return 2
    }
    //함수는 대입 X

    override fun onClick() {
        //interface를 상속한 클래스에서 interface의 함수를 무조건 override 해야한다.
        // 1번째 인터페이스 함수
    }

    override fun onChange() {
        // 2번째 인터페이스 함수
    }
}
```


```kt
class ButtonClick : OnClickListener{
    override val clickValue : Int = 2 // 변수는 init 형태로 override 가능
    override var clickValue2: Int = 1
    //val은 init{}, 생성자에서 init 가능
    //var은 어디서든지 init, change 가능

    fun changeColor(){
        // interface
//        clickValue = 3  -> val change error
        clickValue2 = 3
    }

    //override : 부모의 필드 또는 함수를 자식 클래스

    override fun onClick() {

    }

}
```

