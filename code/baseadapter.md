# 初始化Adapter
```java
MyBaseAdapter adapter = new MyBaseAdapter(this);
```

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

# 自定义内部类MyBaseAdapter和ViewHolder
```java
class MyBaseAdapter extends BaseAdapter {

        private Context context;

        public MyBaseAdapter(Context context) {
            this.context = context;
        }

        @Override
        public int getCount() {
            return listData.size();
        }

        @Override
        public Object getItem(int i) {
            return listData.get(i);
        }

        @Override
        public long getItemId(int i) {
            return i;
        }

        @Override
        public View getView(final int i, View view, ViewGroup viewGroup) {
            com.example.ast.adapter.MyBaseAdapter.ViewHolder holder = null;
            if (view == null) {
                holder = new com.example.ast.adapter.MyBaseAdapter.ViewHolder();
                view = LayoutInflater.from(context).inflate(R.layout.list_item, null);
                holder.img = (ImageView) view.findViewById(R.id.img);
                holder.title = (TextView) view.findViewById(R.id.title);
                holder.viewBtn = (Button) view.findViewById(R.id.button);
                view.setTag(holder);
            } else {
                holder = (com.example.ast.adapter.MyBaseAdapter.ViewHolder) view.getTag();
            }

            holder.img.setImageResource((Integer) listData.get(i).get("img"));
            holder.title.setText((String) listData.get(i).get("title"));

            holder.viewBtn.setOnClickListener(new View.OnClickListener() {

                @Override
                public void onClick(View v) {
                    listData.remove(i);
                    notifyDataSetChanged();
                }
            });

            return view;
        }
    }

    static class ViewHolder {
        public ImageView img;
        public TextView title;
        public Button viewBtn;
    }
```

# 注意要取消list_item中需要操作的控件的焦点
```xml
android:focusable="false"
```