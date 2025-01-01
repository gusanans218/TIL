# DeepLink

1. 기본 딥링크
- 특정 URL을 앱의 특정 화면과 매핑한다
- 사용자가 해당 URL을 클릭하면 매핑된 앱의 화면을 연다
```kt
<activity android:name=".MyActivity">
    <intent-filter>
        <action android:name="android.intent.action.VIEW" />
        <category android:name="android.intent.category.DEFAULT" />
        <category android:name="android.intent.category.BROWSABLE" />
        <data android:scheme="http"
              android:host="www.example.com"
              android:pathPrefix="/path" />
    </intent-filter>
</activity>
```

2. 앱 링크
- 기본 딥링크와 달리 앱 링크는 사용자가 앱을 설치한 경우에만 작동, 설치되지 않은 경우네느 웹페이지로 이동한다.
- 앱 링크를 설정하려면  웹 서버에에  디지털 자산 링크 파일(assetlinks.json)를 추가해야한다
- 매핑이 성공하면 브라우저 대신 앱이 자동으로 열리고 실패하면 앱을 선택할지 웹을 선택할지 묻는 프롬포트가 나타난다.
```kt
<activity android:name=".MyActivity">
    <intent-filter android:autoVerify="true">
    // 해당 속성이 있어야 사용자가 해당 도메인의 URL을 클릭할 때 브라우저가 아닌 앱이 열림
        <action android:name="android.intent.action.VIEW" />
        <category android:name="android.intent.category.DEFAULT" />
        <category android:name="android.intent.category.BROWSABLE" />
        <data android:scheme="https"
              android:host="www.example.com"
              android:pathPrefix="/path" />
    </intent-filter>
</activity>
```

3. 유니버셜 링크
- 안드로이드뿐만 아니라 iOS에서도 작동하는 링크
- 동일한 URL이 iOS에서는 iOS앱으로, 안드로이드에서는 안드로이드 앱으로 연결되도록 설정 가능하다.