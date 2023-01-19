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

## 아이콘 버튼
```xml
<ImageButton
    android:src="@android:drawable/ic_menu_edit"
    android:rotation="180"
    app:tint="@color/black"
/>
```
* ❕ `@android:drawable/ic_menu_edit` `Ctrl + 클릭`하면 더 많은 아이콘을 볼 수 있다.

## 상단 스타일 바꾸기 (ActionBarTheme)
* https://stackoverflow.com/questions/5861661/actionbar-text-color

src/main/res/values/themes.xml
```diff
<resources xmlns:tools="http://schemas.android.com/tools">
    <style name="Theme.프로젝트" parent="Theme.MaterialComponents.DayNight.DarkActionBar">
+       <item name="actionBarTheme">@style/CustomActionBarTheme</item>
    </style>
</resources>
```

src/main/res/values/styles.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <style name="CustomActionBarTheme">
        <item name="actionBarStyle">@style/CustomActionBarStyle</item>
    </style>
    <style name="CustomActionBarStyle">
        <item name="displayOptions">showTitle</item>
        <item name="divider">?attr/dividerVertical</item>
        <item name="height">?attr/actionBarSize</item>
        <item name="background">@color/white</item>
        <item name="titleTextStyle">@style/CustomTitleTextStyle</item>
    </style>
    <style name="CustomTitleTextStyle">
        <item name="android:textSize">32dp</item>
        <item name="android:textStyle">bold|italic</item>
        <item name="android:textColor">@color/black</item>
    </style>
</resources>
```

```diff
- <style name="CustomActionBarTheme">
+ <style name="CustomActionBarTheme" parent="@android:style/Theme.Holo.Light">
```
* `@android:style/Theme.Holo.Light` 추가 하면 `bottom 그림자`가 추가 된다.

```diff
- <style name="CustomActionBarTheme">
+ <style name="CustomActionBarTheme" parent="@android:style/Widget.Button">
```
* `@android:style/Widget.Button` 추가 하면 `button 형식`의 레이아웃을 볼 수 있다.

## RadioButton text없이 가운데 정렬
```xml
<RadioButton
    android:minWidth="0dp"
    android:minHeight="0dp"
    android:layout_gravity="center"
/>
```
