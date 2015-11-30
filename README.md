## 1.MultiRadioGroup
我们都知道RadioGroup控件不能使多行的RadioButton互斥，所以就有了这个控件；

## 2.Screenshots
![image](/screenshots/tem.gif)

## 3.Usages

1. xml布局文件中引用方法：
```
<com.yuxingxin.library.MultiRadioGroup
    android:id="@+id/multi_rg"
    android:layout_width="match_parent"
    android:layout_height="match_parent">
    <RadioGroup
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        >
        <RadioButton
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="任选一"
            />
        <RadioButton
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="任选二"
            />
        ...
        ...

    </RadioGroup>
    <RadioGroup
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        >
        <RadioButton
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="任选一"
            />
        <RadioButton
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="任选二"
            />
        ...
        ...

    </RadioGroup>
</com.yuxingxin.library.MultiRadioGroup>

```

2. 在代码中动态添加方法：
```
MultiRadioGroup multiRadioGroup = (MultiRadioGroup)findViewById(R.id.multi_rg);
multiRadioGroup.addView(child,index,layoutParams);
```

参数：
> 1. child: 子View,一般指RadioGroup
> 2. index: 子View索引
> 3. layoutParams: 布局参数

## 设置监听：
```
MultiRadioGroup multiRadioGroup = (MultiRadioGroup)findViewById(R.id.multi_rg);
multiRadioGroup.setOnCheckedChangeListener(new MultiRadioGroup.OnCheckedChangeListener() {
    @Override
    public void onCheckedChanged(MultiRadioGroup group, int checkedId) {
        RadioButton radioButton = (RadioButton)findViewById(checkedId);
        Toast.makeText(MainActivity.this,radioButton.getText().toString(),Toast.LENGTH_SHORT).show();
    }
});
```

## 4.License
MIT