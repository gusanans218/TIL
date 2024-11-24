# this, context

## 1. `this`

### **1. 현재 클래스의 인스턴스 참조**

- **액티비티(Activity) 내에서의 `this`**: 현재 `Activity`의 인스턴스를 참조할 때 사용
    
    ```kotlin
    class MainActivity : AppCompatActivity() {
        override fun onCreate(savedInstanceState: Bundle?) {
            super.onCreate(savedInstanceState)
            setContentView(R.layout.activity_main)
    
            Toast.makeText(this, "안녕하세요!", Toast.LENGTH_SHORT).show()
        }
    }
    ```
    

### **2. 이벤트 리스너 내에서의 `this`**

- **내부 클래스에서의 `this`**: 이벤트 리스너 내에서 `this`는 리스너 자체를 가리킴
- 외부 `Activity`를 참조하려면 `ActivityName.this` 대신 `ActivityName@` 형식을 사용
    
    ```kotlin
    class MainActivity : AppCompatActivity() {
    
        override fun onCreate(savedInstanceState: Bundle?) {
            super.onCreate(savedInstanceState)
            setContentView(R.layout.activity_main)
    
            val button: Button = findViewById(R.id.button)
            button.setOnClickListener(object : View.OnClickListener {
                override fun onClick(v: View?) {
                    // 'this'는 OnClickListener를 참조
                    // MainActivity를 참조하려면 'this@MainActivity' 사용
                    Toast.makeText(this@MainActivity, "버튼 클릭됨!", Toast.LENGTH_SHORT).show()
                }
            })
    
            // 람다식 사용 시 'this'는 Activity를 가리킴
            button.setOnClickListener {
                Toast.makeText(this, "버튼 클릭됨!", Toast.LENGTH_SHORT).show()
            }
        }
    }
    ```
    

### **프래그먼트에서의 `this`**

- 프래그먼트 내에서는 `this`가 프래그먼트를 가리킴
- `Context`가 필요할 때는 별도로 참조

## 2. `Context` 객체

### **`Context`란?**

`Context`는 애플리케이션과 시스템 간의 브리지 역할

### **`Context`의 종류**

1. **Application Context (`applicationContext`)**
    - **특징**:
        - 애플리케이션의 생명 주기 전체에 걸쳐 존재
        - 애플리케이션 전역에서 사용 가능하며, 메모리 누수를 방지
    - **사용 예시**:
        - 애플리케이션의 전역적인 리소스나 설정에 접근할 때.
        - Toast 메시지와 같은 UI 요소를 표시할 때.

        ```kotlin
        class MainActivity : AppCompatActivity() {
            override fun onCreate(savedInstanceState: Bundle?) {
                super.onCreate(savedInstanceState)
                setContentView(R.layout.activity_main)
        
                val appContext = applicationContext
                Toast.makeText(appContext, "Application Context", Toast.LENGTH_SHORT).show()
            }
        }
        ```
        
2. **Activity Context (`this` 또는 `ActivityName@`)**
    - **특징**:
        - 특정 `Activity`의 생명 주기와 함께 존재
        - UI와 관련된 작업에 주로 사용
    - **사용 예시**:
        - 새로운 액티비티를 시작할 때.
        - 다이얼로그(Dialog)나 팝업(Popup)을 생성할 때.
        
        ```kotlin
        class MainActivity : AppCompatActivity() {
            override fun onCreate(savedInstanceState: Bundle?) {
                super.onCreate(savedInstanceState)
                setContentView(R.layout.activity_main)
        
                val intent = Intent(this, SecondActivity::class.java)
                startActivity(intent)
            }
        }
        ```
        

### **프래그먼트에서의 `Context` 사용**

- **`getContext()`**: 프래그먼트가 액티비티에 연결되어 있으면 `Context`를 반환하고, 그렇지 않으면 `null`을 반환
- **`requireContext()`**: 프래그먼트가 반드시 액티비티에 연결되어 있어야 할 때 사용하며, 그렇지 않으면 예외