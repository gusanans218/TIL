# App Manifest

Manifest 안에 들어있는 것
1. package
    애플리케이션의 고유 식별자 역할을 함
2. 권한
    인터넷 접근 권한 같은 것
    <uses-permission android:name="android.permission.INTERNET" />
3. 구성 요소
    1. activity : 각 액티비티는 intent-filter를 통해 인텐트를 받을 수 있음
    2. service : 백그라운드에서 실행되는 작업을 정의
    3. receiver : 브로드캐스트 수신기를 정의
    4. provider : 애플리케이션 간의 데이터 공유를 가능하게 하는 콘텐츠 제공자를 정의

4. 애플리케이션 메타데이터
    meta-data 추가적인 메타데이터를 애플리케이션에 제공할 수 있다.


## applicationID와 package와의 차이

1. package - in AndroidManifest
    - 소스코드와 리소스파일에서 사용
    - 컴파일 시간에 영향을 미침
    ```kt
    <manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.myapp">
    ```

2. applicationId - in build.gradle
    - 앱의 고유 식별자로 사용
    - 앱이 Google Play 스토어에 배포될 때 이 ID를 기준으로 식별
    ```gradle
   android {
    compileSdkVersion 30
    defaultConfig {
        applicationId "com.example.myapp"
    }
   }
    ```