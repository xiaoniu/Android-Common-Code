# 直通车

### [包含一个ImageView，一个TextView和一个Button的item](https://github.com/xiaoniu/Android-Common-Code/blob/master/code/list_item.xml)
效果如下：

![](http://upload-images.jianshu.io/upload_images/1849253-8d12325383f3fa16.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
### ArrayAdapter，比较简单，直接给出
```java
ArrayAdapter<String> adapter = new ArrayAdapter<String>(this,android.R.layout.simple_list_item_1,getData());
```
三个参数：
* **Context context:** 上下文，一般传this
* **int resource:** list_item索引，一般传android.R.layout.simple_list_item_1
* **List<String> objects或String[] objects:** 数据 

### [SimpleAdapter](https://github.com/xiaoniu/Android-Common-Code/blob/master/code/simpleadapter.md)

### [BaseAdapter](https://github.com/xiaoniu/Android-Common-Code/blob/master/code/baseadapter.md)
    

# Adapter介绍
Adapter是连接后端数据和前端显示的适配器接口，是数据和UI（View）之间一个重要的纽带。在常见的View(List View,Grid View)等地方都需要用到Adapter。如下图直观的表达了Data、Adapter、View三者的关系：

![](http://upload-images.jianshu.io/upload_images/1849253-574d2622de3fd738.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
Android中所有的Adapter一览：
![](http://upload-images.jianshu.io/upload_images/1849253-3bd7ed92cd1bcb49.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

以上参考自：
[xxfeng-Android之Adapter用法总结](http://blog.csdn.net/fznpcy/article/details/8658155)

我的总结是：
* **ArrayAdapter和SimpleAdapter适合只用于显示信息的ListView**
* **ArrayAdapter适合显示一条文本信息的ListView**
* **SimpleAdapter适合显示图文组合信息的ListView**
* **BaseAdapter适合需要操作信息的ListView，就像下图这个ListView中的一个Item，除了展示信息，后面还有一个删除的Button，想要处理这个Button的点击时间就要自己继承BaseAdapter然后处理。**

![](http://upload-images.jianshu.io/upload_images/1849253-8d12325383f3fa16.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)