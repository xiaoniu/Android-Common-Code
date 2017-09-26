# Android 开发常用代码汇总

作为一个程序员，开发时难免会碰到一些记得不太牢的知识点，背的话又有点费劲，背完一段时间不用又会忘掉，每次去网上查的话，又要经过一番信息筛选，浪费时间，所以就把常用的代码都总结一下，下次要用的时候直接就拿出来复制粘贴再做修改就可以了。这个项目也将会持续更新。

## [一、Adapter部分](https://github.com/xiaoniu/Android-Common-Code/blob/master/introduction/Adapter.md)

### [1、包含一个ImageView，一个TextView和一个Button的item](https://github.com/xiaoniu/Android-Common-Code/blob/master/code/list_item.xml)
效果如下：

![](http://upload-images.jianshu.io/upload_images/1849253-8d12325383f3fa16.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 2、ArrayAdapter，比较简单，直接给出

```java
ArrayAdapter<String> adapter = new ArrayAdapter<String>(this,android.R.layout.simple_list_item_1,getData());
```

三个参数：

* **Context context:** 上下文，一般传this
* **int resource:** list_item索引，一般传android.R.layout.simple_list_item_1
* **List<String> objects或String[] objects:** 数据 

### [3、SimpleAdapter](https://github.com/xiaoniu/Android-Common-Code/blob/master/code/simpleadapter.md)

### [4、BaseAdapter](https://github.com/xiaoniu/Android-Common-Code/blob/master/code/baseadapter.md)

## 二、自定义View部分

### [1、自定义属性](https://github.com/xiaoniu/Android-Common-Code/blob/master/code/custom-attrs.md)

## 三、其他

* [Android Studio中的.gitignore文件配置](https://github.com/xiaoniu/Android-Common-Code/blob/master/code/gitignore-code.md)
* [SharedPreferences](https://github.com/xiaoniu/Android-Common-Code/blob/master/code/sharedpreferences-code.md)
* [canvas.drawText绘制居中的文字](https://github.com/xiaoniu/Android-Common-Code/blob/master/code/canvas_draw_text_in_center.md)
* [Material Design Colors](https://github.com/xiaoniu/Android-Common-Code/blob/master/code/colors.xml)
  ![](http://upload-images.jianshu.io/upload_images/1849253-3f6be94bbd53f650.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
