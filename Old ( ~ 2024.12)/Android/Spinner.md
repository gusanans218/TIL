## Spinner

스피너의 주요 메서드

1. setAdapter(Adapter 설정)
- 스피너에 데이터를 설정하는 프로퍼티이다
```kt
val spinner:Spinner = findViewById(R.id.spinner)
val items = arrayOf("item1", "item2","item3")
val adapter = ArrayAdapter(this, android.R.layout.simple_spinner_item,items)
adapter.setDropDownViewResource(android.R.layout.simple_spinner_dropdown_item)
spinner.adapter = adapter
```

2. getSelectedItem() 
- 선택된 항목을 반환한다
```kt
val selectedItem = spinner.selectedItem
```

3. getSelectedItemId()
- 선택된 항목의 ID를 반환합니다
```kt
val selectedItemId = spinner.selectedItemId
```

4. getSelectedItemPosition()
- 선택된 항목의 위치를 반환합니다
```kt
val position = spinner.selectedItemPosition
```

5. setOnItemSelectedListener(AdapterView.OnItemSelectedListener listener)
- 스피너 항목이 선택되었을 때 호출되는 리스너를 설정합니다
```kt
spinner.onItemSelectedListener = object : AdapterView.OnItemSelectedListener {
    override fun onItemSelected(parent: AdapterView<*>, view: View?, position: Int, id: Long) {
        val selectedItem = parent.getItemAtPosition(position).toString()
        Toast.makeText(parent.context, "Selected: $selectedItem", Toast.LENGTH_LONG).show()
    }

    override fun onNothingSelected(parent: AdapterView<*>) {
        // 아무것도 선택되지 않았을 때의 동작
    }
}
```

6. setSelection(int position)
- 주어진 위치의 항목을 선택합니다
```kt
val spinner.setSelection(position)
```


사용 예시
```kt
class MainActivity : AppCompatActivity() {

    private lateinit var spinner: Spinner

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        spinner = findViewById(R.id.spinner)

        // 스피너에 데이터 설정
        val adapter = ArrayAdapter.createFromResource(this, R.array.planets_array, android.R.layout.simple_spinner_item)
        adapter.setDropDownViewResource(android.R.layout.simple_spinner_dropdown_item)
        spinner.adapter = adapter

        // 선택된 항목 리스너 설정
        spinner.onItemSelectedListener = object : AdapterView.OnItemSelectedListener {
            override fun onItemSelected(parent: AdapterView<*>, view: View?, position: Int, id: Long) {
                val selectedItem = parent.getItemAtPosition(position).toString()
                Toast.makeText(parent.context, "Selected: $selectedItem", Toast.LENGTH_LONG).show()
            }

            override fun onNothingSelected(parent: AdapterView<*>) {
                // 아무것도 선택되지 않았을 때의 동작
            }
        }
    }
}

```



