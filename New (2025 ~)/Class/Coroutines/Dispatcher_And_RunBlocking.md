## runBlocking
- runBlocking은 호출한 스레드를 차단(blocking) 하면서 실행되는 코루틴을 생성합니다.
- 이 코루틴은 내부 작업이 모두 종료될 때까지 호출한 스레드를 점유합니다.
     - 일반적으로 테스트 코드나 코루틴 환경이 아닌 곳에서 코루틴 실행 시 사용됩니다.
    - 주의: 메인 스레드에서 사용하는 것은 비효율적입니다.

`runBlocking = Run (실행) + blocking (차단)
`
```
import kotlinx.coroutines.*

fun main() {
    println("Start")
    runBlocking {
        println("Inside runBlocking")
        delay(1000L) // 1초 대기
        println("End of runBlocking")
    }
    println("Finish")
}
```

## CoroutineDispatcher
- CoroutineDispatcher는 코루틴을 특정 스레드 또는 스레드 풀에서 실행시키는 객체입니다.
- 요청받은 코루틴 작업을 작업 대기열에 적재하고, 사용 가능한 스레드가 있을 때 실행합니다.


## 주요 Dispatchers
### 1) Dispatchers.IO
- 입출력(I/O) 작업에 최적화된 디스패처.
- 네트워크 요청, 파일 읽기/쓰기, 데이터베이스 작업 등.   
    - 스레드 수:
64와 JVM에서 사용할 수 있는 프로세서 수 중 더 큰 값.
(예: 프로세서가 8개인 경우, 64개의 스레드 사용 가능)


**limitedParallelism(n): 별도의 스레드 풀을 만들어 병렬 작업 제한.  
사용 사례: 다른 작업과 독립적으로 실행해야 하는 중요 작업.**

```
import kotlinx.coroutines.*

fun main() = runBlocking {
    launch(Dispatchers.IO) {
        println("Running on IO Dispatcher: ${Thread.currentThread().name}")
        delay(1000L)
        println("Completed IO task")
    }
}
```

### 2) Dispatchers.Default
- CPU 바운드 작업에 최적화된 디스패처.
- 이미지/동영상 처리, 대규모 데이터 연산 등 끊임없이 연산이 필요한 작업.   
    - 스레드 수:머신의 프로세서 수와 2 중 큰 값.
(머신 환경마다 값이 다름)

**limitedParallelism(n): 병렬 작업을 n개로 제한.**

```
import kotlinx.coroutines.*

fun main() = runBlocking {
    launch(Dispatchers.Default) {
        println("Running on Default Dispatcher: ${Thread.currentThread().name}")
        for (i in 1..5) {
            println("Processing $i on ${Thread.currentThread().name}")
        }
    }
}
```

### 3) Dispatchers.Main
- UI 작업(메인 스레드 작업)을 위한 디스패처.

기본 코루틴 라이브러리에는 구현체가 없음.

사용하려면 Android 코루틴 라이브러리를 추가해야한다   

```implementation "org.jetbrains.kotlinx:kotlinx-coroutines-android:1.x.x"```

- 코루틴을 작업 대기열에 적재한 뒤, 메인 스레드가 비었을 때 실행.
- 코루틴이 많이 쌓이면 UI 작업 지연 가능성 존재.

### 4) Dispatchers.Main.immediate
- 메인 스레드에서 즉시 실행을 보장하는 디스패처.

- 메인 스레드에서 실행 요청된 경우, 작업 대기열을 거치지 않고 즉시 실행.
- 백그라운드 스레드에서 실행 요청 시에는 Dispatchers.Main과 동일하게 동작.

```
import kotlinx.coroutines.*

fun main() = runBlocking {
    launch(Dispatchers.Main) {
        println("Main Dispatcher: ${Thread.currentThread().name}")
    }

    launch(Dispatchers.Main.immediate) {
        println("Immediate Main Dispatcher: ${Thread.currentThread().name}")
    }
}
```
### 4. 부모-자식 코루틴의 디스패처 상속
- 부모 코루틴에서 설정한 디스패처는 자식 코루틴에서 기본적으로 상속됩니다.
- 자식 코루틴에 별도의 디스패처를 명시하지 않으면 부모의 디스패처를 따릅니다.

```
import kotlinx.coroutines.*

fun main() = runBlocking(Dispatchers.IO) { // 부모 코루틴은 IO Dispatcher
    launch { // 자식 코루틴 1
        println("Child Coroutine 1: ${Thread.currentThread().name}")
    }
    launch(Dispatchers.Default) { // 자식 코루틴 2
        println("Child Coroutine 2: ${Thread.currentThread().name}")
    }
}
```