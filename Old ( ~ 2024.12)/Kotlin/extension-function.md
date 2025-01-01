# Extension Function (확장함수)

- 클래스에 새로운 함수를 추가하는 개념
- 상속을 사용하지 않고도 기존 클래스에 기능을 확장할 수 있다는 점

```kt
fun 클래스이름.함수이름(매개변수들): 반환타입 {
    // 함수의 구현
}
```

## 확장함수의 제약사항
1. 클래스의 private 멤버에 접근할 수 없다   
    - 해당 클래스의 private 속성이나 메소드에 접근할 수 없다.   
        확장 함수가 실제로 클래스의 내부에 존재하지 않기 때문이다

2. 멤버 함수가 우선권을 가진다  
    - 확장 함수와 클래스의 멤버 함수가 이름이 동일할 경우, 멤버 함수가 우선적으로 호출된다.   
    - 동일한 이름을 가진 멤버 함수와 확장 함수를 동시에 사용할 수는 없다

## 확장함수가 필요한 이유
1. 기존 코드 수정 없이 클래스 기능 확장
2. 가독성 향상 및 유연성 