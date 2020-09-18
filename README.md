# Android-learning

## 教程基于《Android Studio 应用程序设计（第2版）》 ——张思民著

### 第1章  Android系统及其开发过程

#### 第1节 Android系统概述

**Android系统由操作系统，中间件，用户程序界面和应用软件等组成，其特点有：**

- 系统开放性：Android系统从底层操作系统直到最上层的应用程序都是开放的

- 应用程序平等性：Android自带的程序和程序开发人员开发的应用程序是平等的

- 开发方便性：强大的API库支持

- 硬件丰富性

**Android系统的体系结构：**

- 应用程序

- 应用程序框架：活动页面管理、窗口管理、内容供应、视图系统、包管理、电话管理、资源管理、位置管理、通知管理
  
- 系统运行库：程序库 / Android运行时库

- Linux内核：安全性、内存管理、进程管理、网络协议栈、驱动模型

**安卓开发的分类：**

- 系统移植开发

- Android应用程序开发

可百度

#### 第4节 Android应用程序的开发过程

- 在AS集成环境中生成应用项目框架

- 修改和编写XML源程序

- 修改或编写JAVA源程序

- 调用模拟器运行应用程序

#### 第5节  Android项目结构

**app模块目录结构：**

**Android应用程序结构分析：**

一个Android应用程序通常由Activity类程序（JAVA）和用户界面布局（XML）文档组成。逻辑控制层和表现层是分开设计的。

### 第2章  Android用户界面的设计

#### 第1节  用户界面组件包Widget和View类

**Widget：提供了丰富多彩的用户界面组件**

|可视化组件|说明|
|----|----|
|Button|按钮|
|CalendarView|日历视图|
|CheckBox|复选框|
|Edittext|文本输入框|
|ImageView|图片|
|ListView|列表视图|
|RadioGroup|单选按钮|
|Spinner|下拉列表|
|TextView|文本标签|
|WebView|浏览器视图|
|Toast|消息提示|


**View：用户界面组件共同的父类**

对于View及其子类的属性，可以在在XML配置，也可以在Java代码中动态配置

|属性|对应方法|说明|
|----|----|----|
|android:background|setBackgroundColor(int color)|设置背景颜色|
|android:id|setId(int)|为组件设置Id|
|android:alpha|setAlpha(int)/findViewById()|透明度/关联Id|
|android:visibility|setVisibility(int)|设置组件可见性|
|android:clickable|setClickable(boolean)|是否接受点击事件|


#### 第2节  文本标签TextView与按钮Button

按钮是TextView的子类

#### 第2节  文本标签TextView与按钮Button

见示范代码

#### 第3节 文本编辑框EditText

继承自TextView

#### 第4节  Android布局管理

Andrid系统的布局管理指的是在XML布局文件中设置组件的大小、间据、排列及对齐方式等。
Android常见的布局方式有LinearLayout，FrameLayout，TableLayout，RelativeLayout，GridLayout

- 线性布局是所有布局中最常用的一种布局方式，要么水平线性布局，要么垂直线性布局

- 帧布局是将组件放置到左上角位置，当添加多个组件时后面的组件将遮盖之前的组件

- 表格布局是将页面划分成由行、列组成的单元格,列数由shrinkColumns定义，行由TableView标签定义

- 相对布局是采用相对其他组件位置的布局方式。在相对布局中通过指定id关联其他组件与之右对齐、上下对齐或以屏幕中央等方式来排列组件

- 网格布局是设置区域为若干行和若干列的网格


#### 第5节 进度条和选项按钮

见示范代码

#### 第6节 图像显示类ImageView和画廊组件类Gallery

ImageView比较混淆的是scaleType属性值：

|scaleType属性值常量|说明|
|----|----|
|matrix|用矩阵来绘图|
|fitXY|拉伸图片（不按宽高比例）以填充View|
|fitStart|按比例拉伸图片，使得高度为View的高度，且显示在View左边|
|fitCenter|按比例拉伸图片，使得高度为View的高度，且显示在View中间|
|fitEnd|按比例拉伸图片，使得高度为View的高度，且显示在View右边|
|center|按原图大小显示图片，当宽高大于View宽高时则截取图片中间部分显示|
|centerCrop|按比例放大原图直至等于某边View的宽高显示|
|centerInside|当原图宽高等于View的宽高时按原图大小居中显示，否则将原图缩放至View的宽高居中显示|

Gallery类常与图片切换器ImageSwitcher配合使用，用图片切换器ImageSwitcher类展示图片效果。使用ImageSwitcher时必须用ViewFactory接口的makeView()方法创建视图。

Gallery类常用的属性方法
|元素属性|说明|
|----|----|
|spacing|设置图片之间的间距，以像素为单位|
|unselectedAlpha|设置未选中图片的透明度|
|animationDuration|设置当布局变化时动画转换所需的时间|


ImageSwitcher常用方法
|setInAnimation|绘制的动画对象进屏幕的方式|
|setOutAnimation|绘制的动画对象离开屏幕的方式|
|setImageResource|设置显示的初始图片|
|showNext|展示下一个视图|
|showPrevious|展示上一个视图|

程序设计步骤：

- 在布局文件中声明画廊组件Gallery和图片切换器ImageSwitcher，采用表格布局

- 把事先准备好的图片文件复制到项目的drawable中，在Activity创建一个图像文件数组，其数组的元素为图片文件

- 在Activity中创建画廊组件Gallery和图片切换器ImageSwitcher组件的实例对象

- 在Activity中创建一个实现Viewfactory接口的内部类，重写该类的makeView()方法建立ImageView视图。ImageSwitcher通过该图像视图显示放大的图片

- 在Activity中创建一个BaseAdapter适配器子类的内部类，用于安排放在画廊中图片文件及显示方式

#### 第7节 消息提示类Toast

消息Toast有默认方式、自定义方式和带图标方式

#### 第8节 列表组件

ListView类是Android开发中经常用到的组件，该组件必须和适配器配合使用，由适配器提供显示样式和显示数据。

ListView类

ListActivity类

当整个Activity中只有一个ListView组件时可以使用ListActivity，默认绑定了一个ListView（可用geiListView获取得到），并提供了一些与ListView相关的操作


#### 第8节 列表组件Slidingdraw

见示范代码


### 第3章  多个用户界面的程序设计

#### 第1节  页面的切换和传递参数值

Intent是Android系统中一种运行时的绑定机制，连接两个不同的组件。通俗理解，Intent就是不同组件的媒介，专门提供组件互相调用的相关信息。

Intent属性有：

|属性名|说明|
|----|----|
|ACTION_MAIN|标识Activity为一个程序的开始|
|ACTION_GET_CONTENT|允许用户选择图片或录音等数据|
|ACTION_SEND|发送邮件|
|SMS_RECEIVED|接收邮件|
|ACTION_ANSWER|处理呼入的电话|
|ACTION_CALL_BUTTON|按下拨号键|
|ACTION_CALL|呼叫电话号码|

Activity页面之间的切换，一般有如下流程：

（1）创建一个Intent对象

（2）调用Activity的startActivity(intent)方法

我们还希望能够在不同的Activity之间传递数据，这个时候需要用到Bundle类

Buddle类是用于为字符串与某组件对象建立映射关系的组件，一般来说，有如下流程：

（1）在原Activity新建Intent对象和Buddle对象

（2）其中Intent和上面一样，而Buddle对象则可参照以下写法：`bundle.putString("text",txt.getText().toString())`

（3）把Buddle对象床传给Intent对象：`intent.putExtras(bundle)`

（4）另外一个Activity，调用：

```java
bundle = this.getIntent().getExtras();
String str = bundle.getString("text");
```


#### 第2节  菜单设计

Android的菜单可以分为三类：Option Menu（选项菜单），Context Menu（上下文菜单），Sub Menu

|方法|说明|
|----|----|
|onCreateOptionMenu|初始化菜单|
|onPrepareOptionsMenu|显示之前调用|
|onOptionsMenuClosed|菜单关闭时调用|
|onOptionsItemSelected|监听方法|

创建选项菜单的步骤：

（1）重写Activity的onCreateOptionMenu方法，当菜单第1次被打开时调用

（2）调用Menu的add方法添加菜单项（MenuItem）

（3）重写Activity的onOptionsItemSelected方法，响应点击事件

见样例

上下文菜单：

任何视图都可以注册上下文菜单，见样例


#### 第3节  对话框

Android提供了4种常用的对话框：

- AlertDialog：消息对话框

- ProgressDialog：进度条对话框

- DatePickerDialog：日期选择对话框

- TimePickerDialog：时间选择对话框

AlertDialog：

|方法|说明|
|----|----|
|AlertDialog.Builder|构造方法|
|create|创建AlertDialog对象|
|setTitle|设置标题|
|setIcon|设置图标|
|setMessage|设置提示信息|
|setItems|设置对话框要显示的一个list|
|setPositiveButton|添加yes按钮|
|setNegativeButton|添加no按钮|
|show|显示对话框|
|dismiss|关闭对话框|

创建流程：

```java
Builder dialog = new AlertDialog().Builder(Context);

dialog.setTitle();
dialog.setIcon();
dialog.setMessage();
dialog.setPositiveButton();

dialog.create();
dialog.show();
```



### 第4章  图形与多媒体设计


### 第5章  后台服务与系统服务

#### 第1节  后台服务Service

Service服务的常用方法

|方法|说明|
|----|----|
|onCreate|创建后台服务|
|onStartCommand|启动一个后台服务|
|onDestroy|销毁后台服务，并删除所有调用|
|sendBroadcast|发送广播|
|onBind|与服务通信信道进行绑定|
|onUnbind|撤销与通信信道的绑定|

设计一个后台服务的应用程序大致有以下几个步骤：

（1）创建Service的子类：
- 编写onCreate()方法，创建后台服务
- 编写onStartCommand()方法，启动后台服务
- 编写onDestory()方法，终止后台服务，并删除所有调用

（2）创建启动和控制Service的Activity：
- 创建Intent对象，建立Activity与Service的关联
- 调用Activity的startService方法启动Service后台服务
- 调用Activity的stopService方法关闭后台服务

（3）修改AndroidManifest.xml









