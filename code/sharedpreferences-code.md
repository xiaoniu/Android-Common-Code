* 声明SharedPreferences型变量
```java 
private SharedPreferences sp;
```
* 创建一个SharedPreferences，第一个参数是数据保存文件的名字，第二个参数是权限
```java
sp = context.getSharedPreferences("sp_name",Context.MODE_PRIVATE);
```
* 提交数据，第一个参数是key，第二个是值
```java
//第一种方式
sp.edit().putInt("value",1).commit();
sp.edit().putString("name","张三").commit();
//第二种方式
SharedPreferences.Editor editor = sp.edit();
editor.putInt("value",1);
editor.putString("name","张三");
editor.commit();
```
* 查询数据，第一个参数是key，第二个参数是默认值
```java
sp.getInt("value",0);
sp.getString("name","张三");
```