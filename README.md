# Android

## 본문에 paddingTop 지우기
src/main/res/layout/activity_main.xml
```diff
- android:paddingTop="?attr/actionBarSize"
```
* `actionBarSize`는 상단 해더의 크기

## 백터 아이콘
```sh
res > New > Vetor Asset > Clip Art > 검색 후 Next, Finish > 아이콘 파일 생성
```

## 상단 스타일 바꾸기 (ActionBarStyle)
src/main/res/values/themes.xml
```diff
<resources xmlns:tools="http://schemas.android.com/tools">
    <style name="Theme.프로젝트" parent="Theme.MaterialComponents.DayNight.DarkActionBar">
+       <item name="actionBarStyle">@style/CustomActionBarStyle</item>
    </style>
</resources>
```

src/main/res/values/styles.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <style name="CustomTitleTextStyle">
        <item name="android:textSize">32dp</item>
        <item name="android:textStyle">bold|italic</item>
        <item name="android:textColor">@color/black</item>
        <item name="android:textAlignment">center</item>
    </style>
    <style name="CustomActionBarStyle">
        <item name="displayOptions">showTitle</item>
        <item name="divider">?attr/dividerVertical</item>
        <item name="height">?attr/actionBarSize</item>
        <item name="background">@color/black</item>
        <item name="titleTextStyle">@style/CustomTitleTextStyle</item>
    </style>
</resources>
```
