#### 环境
* dataBinding元素添加到build.gradle
```
    android {
        ...
        dataBinding {
            enabled = true
        }
    }
```
**即使应用模块不直接使用数据绑定，也必须为依赖于使用数据绑定的库的应用模块配置数据绑定**
即：不仅lib_module中引入，app_module也需要引入

#### 布局绑定
* xml
```
    <?xml version="1.0" encoding="utf-8"?>
    <layout xmlns:android="http://schemas.android.com/apk/res/android">
       <data>
           <variable name="user" type="com.xxx.UserBean"/>
       </data>
       <LinearLayout
           android:orientation="vertical"
           android:layout_width="match_parent"
           android:layout_height="match_parent">
           <TextView android:layout_width="wrap_content"
               android:layout_height="wrap_content"
               android:text="@{user.firstName}"/>
           <TextView android:layout_width="wrap_content"
               android:layout_height="wrap_content"
               android:text="@{user.lastName}"/>
       </LinearLayout>
    </layout>

    data class User(val firstName: String, val lastName: String)
```
* Binding类生成


* 数据使用
```
  //Test
  val binding: ActivityMainBinding = ActivityMainBinding.inflate(getLayoutInflater())

  override fun onCreate(savedInstanceState: Bundle?) {
      super.onCreate(savedInstanceState)
      val binding: ActivityMainBinding = DataBindingUtil.setContentView(
              this, R.layout.activity_main)
      binding.user = User("Test", "User")
  }
  //Fragment, ListView, or RecyclerView adapter
  val listItemBinding = ListItemBinding.inflate(layoutInflater, viewGroup, false)
  // or
  val listItemBinding = DataBindingUtil.inflate(layoutInflater, R.layout.list_item, viewGroup, false)
```

#### 表达式
```
  android:text="@{String.valueOf(index + 1)}"
  android:visibility="@{age > 13 ? View.GONE : View.VISIBLE}"
  android:transitionName='@{"image_" + id}'
  android:text="@{user.displayName ?? user.lastName}"
  or
  android:text="@{user.displayName != null ? user.displayName : user.lastName}"
```

#### 环境
