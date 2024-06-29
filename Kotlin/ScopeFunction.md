```kt
fun main(){
    val s = ScopeExample()
    s.main()
}

private class VariableClass{
    var value = ""
}



private class ScopeExample{
    val v = VariableClass()

    fun main(){
        // variable.scope function 형태로 기록한다
        println(v.value)

        val applyValue = v.apply {
            value = "after apply"
        }

        //apply는 variable을 그대로 반환하지만, apply 함수 내부의 코드나 수정사항은 모두 적용 시킨 채 variable를 반환한다

        println(applyValue.value)

        val letValue = v.let {
            it.value = "after let"
            it.value
        }

        // let 함수는 variable 부분의 변수가 it이 되며, 가장 마지막 코드가 반환이 된다

        println(letValue)

        val runValue = v.run {
            value = "after run value length is ${value.length}"
            this
        }

        // run 함수는 variable이 this가 되며, let과 비슷하게 가장 마지막 코드가 반환이 된다

        println(runValue.value)

        val alsoValue = v.also {
            it.value = "after also"
            it.value
        }

        // also 함수는 variable이 it이 되며 also 함수 내의 코드가 모두 적용된 후 variable이 반환된다

        println(alsoValue.value)
    }
}
```s