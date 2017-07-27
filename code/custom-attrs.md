# 在res/values/下创建一个名为attrs.xml的文件
```
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <declare-styleable name="MyTextView">
        <attr name="mText" format="string" />
        <attr name="mTextColor" format="color" />
        <attr name="mTextSize" format="dimension" />
    </declare-styleable>
</resources>
```
# 在布局文件中引用这些属性

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:myattrs="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="com.example.ast.customview.MainActivity">

    <com.example.ast.customview.MyTextView
        android:layout_width="200dp"
        android:layout_height="100dp"
        myattrs:mTextSize="25sp"
        myattrs:mText="富强民主文明和谐"
        myattrs:mTextColor ="#0000ff"
        android:background="#ff0000" />

</RelativeLayout>
```
注意一定要加上：
```
 xmlns:myattrs="http://schemas.android.com/apk/res-auto"
```
#在自定义View的构造方法中获得属性值
```
        //获取自定义属性的值
        TypedArray a = context.getTheme().obtainStyledAttributes(attrs, R.styleable.MyTextView, defStyleAttr, 0);
        mText = a.getString(R.styleable.MyTextView_mText);
        mTextColor = a.getColor(R.styleable.MyTextView_mTextColor, Color.BLACK);
        mTextSize = a.getDimension(R.styleable.MyTextView_mTextSize, 100);
        a.recycle();  //注意回收
```
之后将这些值设置给View就可以了