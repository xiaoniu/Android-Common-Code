# 初始化adapter
```java
        SimpleAdapter adapter = new SimpleAdapter(this,getData(),R.layout.simple_list_item,
                new String[]{"img","title"},
                new int[]{R.id.img,R.id.title});
```

五个参数：
* **Context context:** 上下文，一般传this
* **List<? extends Map<String, ?>> data** List<Map<String, Object>>型数据
* **int resource:** list_item索引，一般传自定义的list_item
* **String[] from:** map中的key组成的字符串数组 
* **int[] to:** 自定义list_item中的控件id

# 获取数据
```java
    private List<Map<String, Object>> getData() {
        List<Map<String, Object>> list = new ArrayList<Map<String, Object>>();

        Map<String, Object> map = new HashMap<String, Object>();
        map.put("title", "打狗棒法");
        map.put("img", R.mipmap.dagoubangfa);
        list.add(map);

        map = new HashMap<String, Object>();
        map.put("title", "飞龙在天");
        map.put("img", R.mipmap.feilongzaitian);
        list.add(map);

        map = new HashMap<String, Object>();
        map.put("title", "九阴白骨爪");
        map.put("img", R.mipmap.jiuyinbaiguzhao);
        list.add(map);

        return list;
    }
```