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

#### 第1节  绘制几何图形

绘制的基本流程：
- 创建一个View子类，重写其OnDraw方法
- 在View的子类视图中使用画布对象Canvas绘制图形
- 使用invalidate方法刷新画面

#### 第2节  触摸屏事件处理

见示例代码

#### 第3、4节  多媒体播放技术（音频和视频）

**1、android.media中的主要类：**

|类名|说明|
|----|----|
|MediaPlayer|支持流媒体，用于播放音频和视频|
|MediaRecorder|用于录制音频和视频|
|AudioManager|控制音量|
|AudioRecord|用于记录从音频输入设备产生的数据|
|SoundPool|用于管理和播放应用程序的音频资源|

**2、重点：多媒体处理播放器MediaPlayer：**

|方法|说明|
|----|----|
|create|创建|
|getCurrentPosition|获得当前的播放位置|
|Pause|暂停|
|Prepare|准备播放文件，同步|
|PrepareAsync|准备播放文件，异步|
|release|释放对象|
|reset|重置对象|
|seekTo|指定文件的播放位置|
|setDataSource|设置多媒体数据来源|
|setOnCompletionListener|监听文件播放完毕|
|start|开始播放|
|stop|结束播放|

生命周期图：

[MediaPlayer的生命周期](https://img-my.csdn.net/uploads/201005/26/521376_1274912556IBBI.gif)

使用的一般流程：

1、构建MediaPlayer对象，此处注意：

- 播放SD卡上的音乐文件需要使用new方式创建对象
- R.raw中的音乐文件需要使用create方法创建对象，这里create已经隐含了初始化及同步的方法

2、设置播放文件（SD、Network上文件）：setDataSource

3、同步

4、播放

5、释放

**3、视频播放：**

Android中的视频播放一共有两种方式：应用媒体播放器组件MediaPlayer和应用视频视图组件VideoView

- MediaPlayer：与播放音频的不同，播放视频的承载体必须是实现了表面视图处理接口（surfaceHolder）的视图组件，即需要使用SurfaceView组件来显示播放的视频图像

- VideoView：经常用来播放视频文件，见样例。其常见方法：

|方法|说明|
|----|----|
|getBufferPercentage|获得缓冲区的百分比|
|getCurrentPosition|获得当前位置|
|onTouchEvent|处理触屏时间|
|setMediaController|设置媒体控制器|
|setVideoPath|设置视频文件的路径名|
|setVideoURI|设置视频文件的URI|
|start|播放|
|stop|结束|





#### 第5节  录音与拍照

MediaRecorder类可以录制音频和视频：

|方法|说明|
|----|----|
|MediaRecorder|构造函数|
|setAudioSource|设置音频源|
|setAudioEncoder|设置音频编码格式|
|setVideoSource|设置视频源|
|setVideoEncoder|设置视频编码格式|
|setVideoFrameRate|设置视频帧速率|
|setVideoSize|设置视频录制画面大小|
|setOutputFormat|设置输出格式|
|setOutputFile|设置输出路径|
|prepare|准备录制|
|start|开始录制|
|stop|停止录制|
|restart|重置|
|release|释放资源|

录音流程：

（1）创建录音对象：MediaRecorder r = new MediaRecorder()

（2）设置音频源：r.setAudioSource(MediaRecorder.AudioSouce.MIC)

（3）设置输出格式：r.setOutputFormat(MediaRecorder.OutputFormat.THREE_GPP)

（4）设置编码格式：r.setAudioEncoder(MediaRecorder.AudioEncoder.AMB_NB)

（5）设置文件输出路径：r.setOutputFile(path)

（6）准备录制：r.prepare()

（7）开始录制：r.start()

（8）停止录制：r.stop()  r.reset()

（9）释放资源：r.release()

使用Camera类可以获取当前设备中的照相机服务接口：

|方法|说明|
|----|----|
|open|创建一个照相机对象|
|getParameters|Camera.Parameters对象|
|setParameters|设置照相机参数|
|setPreviewDisplay|设置取景预览|
|startPreview|启动照片取景预览|
|stopPreview|停止照片取景预览|
|release|释放资源|
|takePicture|拍照|

使用照片服务的流程：

（1）创建照相机对象：通过Camera类的open方法创建一个照相机对象：Camera c = Camera.open()

（2）设置参数：创建设置照相机参数的Parameters对象，并设置相关参数

（3）预览照片

（4）拍照

（5）停止拍照

见样例

#### 第6节  动画技术

Animations是一个实现Android UI界面动画效果的API，Animations提供了一系列的动画效果，可以进行旋转、缩放、淡入淡出等，可以运用于绝大多数的控件中。

- 补间动画：只需指定开始、结束的关键帧，变化中的其他帧由系统计算，不必一帧一帧自定义。

- 逐帧动画：创建一个Drawable序列，按照指定的时间间隔一个一个显示

- 属性动画：补间动画其实不改变对象的属性（位置等），而属性动画可以直接改变View对象的属性值。

**1、补间动画**

- Alpha：淡入淡出效果

- Scale：缩放效果

- Rotate：旋转效果

- Translate：移动效果


**2、属性动画**

属性动画就是通过控制对象中的属性值而产生的动画。

- ValueAnimation类：属性动画的运行机制是通过不断对值进行操作来实现的，而初始值和结束值之间的动画过渡就是ValueAnimation类来负责计算的。此类自动帮助用户完成从初始值到结束值之间平滑地过渡。

- ObjectAnimation类：见样例




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


#### 第2节  信息广播机制Broadcast

（1）创建Intent对象，设置Intent对象的action属性。这个action属性是接收广播数据的标识，只有注册了相同action属性的广播接收器才能收到发送的广播数据。

```java
Intent intent = new Intent();
intent.setAction("abc");
```

（2）编写需要广播的信息内容：

```java
intent.putExtra("hello", ""This is the first method");
sendBroadcast(intent);
```

（3）编写一个继承BroadcastReceiver的子类作为广播接收器，该对象是接收广播信息并对信息进行处理的组件，重写onReceive方法

（4）在配置文件中注册广播接受类

（5）销毁广播接收器


#### 第3节  常见系统服务

系统通知服务



#### 第4节  系统功能的调用





### 第6章  网络通信技术

#### 第1节  Web视图

WebView类：

|方法|说明|
|----|----|
|loadUrl|加载网页页面|
|loadData|加载HTML格式的Web视图|
|reload|重新加载|
|getSettings|获取WebSettings对象|
|goBack|返回|
|goForward|前进|
|clearHistory|清空历史|


使用流程：

（1）设置WebView的基本信息：

- 若访问的页面含有js，则`webview.getSettings().setJavaScriptEnabled(true)`
- 触摸焦点起作用：`requestFocus`
- 取消滚动条：`this.setScrollBarStyle(SCROLLBARS_OUTSIDE_OVERLAY)`

（2）设置WebView要显示的网页：
```java
webView.loadUrl("http....."); // 互联网
webView.loadUrl("ftp....."); // 本地文件
```

（3）添加网络权限


#### 第2节  TCP网络通信程序设计

见样例

**应用Callable接口实现多线程Socket编程**

Callable接口和Runnable接口的区别在于：

- Callable接口中定义的方法是call，Runnable接口中定义的方法是run

- call方法可以抛出异常，run方法不能抛出异常

- Callable接口执行完任务之后可以有返回值，Runnable接口执行完任务之后没有返回值

- 运行Callable接口任务可以返回一个Future对象，该对象是异步计算的结果。用户通过Future对象可以了解任务的执行情况，既可以取消任务的执行，还可以获取任务的执行结果

见样例

### 第7章  应用Volley框架访问Web服务器

#### 第1节  Volley框架及其应用

Android开发团队意识到有必要对Http通信操作进行简化，于是在2013年推出了一个新的网络框架——Volley，Volley既可以进行HTTP通信，也可以加载图片等。它的设计目标就是非常适合进行数据量不大但通信频繁的网络操作。

添加`compile group: 'com.mcxiaoke.volley', name: 'library', version: '1.0.19'`至Gradle即可

Volley在处理数据的接收和发送时使用的是JSON格式，JSON是一种轻量级的数据交换格式，成为网络传输中理想的数据交换语言。

Volley的基本工作原理：

首先由主线程（应用程序）发起一条HTTP请求，将请求添加到缓存队列中，然后由缓存调度队列中取出一个请求，在缓存中解析并作出相应，最后将解析后的相应发送给主线程。在Volley内部创建两个线程，一个为缓存调度线程，一个为网络调度线程，优先在缓存中解析并响应请求，如果缓存不能被解析，则由网络线程使用HTTP发送请求给远程Web服务器解析。这里面涉及到几个重要对象：RequesrQueue（用来执行请求的请求队列）、Request（用来构造一个请求对象）。Request对象有以下几种类型：

- StringRequest：响应的主体为字符串
- JsonArrayRequest：发送和接收Json数组
- JsonObjectRequest：发送和接收JSON对象
- ImageRequest：发送和接收Image图像对象

Volley使用方法：

（1）创建一个RequestQueue对象

（2）为了发出一条HTTP请求，还需要创建一个StringRequest对象，这个对象构造函数的参数包括：目的服务器的URL，服务器响应成功的回调函数和服务器响应失败的回调函数

（3）将这个StringRequest对象添加到RequestQueue里面

（4）记得添加网络权限

#### 第2节  应用Volley框架设计网络音乐播放器

见我的主页仓库项目

### 第8章  数据存储技术

#### 第1节  SQLite本地数据库

类似于JDBC数据库技术

#### 第2节  文件处理（Java回顾）

1、文件与目录管理——File类

API说明：

|方法|说明|
|----|----|
|exists|判断文件或者目录是否存在|
|isFile|判断对象是否为文件|
|isDirectory|判断对象是否为目录|
|getName|返回文件名、目录名|
|getPath|返回路径|
|length|返回文件的大小|
|renameTo|重命名|
|delete|删除|
|mkdir|创建当前目录下的子目录|

2、文件流

- FileOutputStream：字节文件输出流
- FileInputStream：字节文件输入流
- FileReader：字符文件输入流
- FileWriter：字符文件输出流

3、读写SD卡

（1）环境变量访问类：Environment

- 获取当前存储设备状态：getExternalState

- 获取SD卡的根目录：getExternalStorageDirectory

（2）设置读写SD卡权限：

判断是否具有对SD卡进行读写的权限：Environment.getExternalStorageState().equals(Environment.MEDIA_MOUNTED)

Manifest配置：
见文件操作综合案例

ps：[如何访问手机内部存储？](https://blog.csdn.net/msn465780/article/details/78538225)

#### 第3节  轻量级存储SharedPreferences

Android系统提供了一个存储少量数据的轻量级数据存储方式SharedPreferences，该存储方式类似于Web程序中的Cookie，通常用它来保存一些配置文件数据、用户名、密码等。

SharedPreferences采用key-value的形式来组织和管理数据，其数据存储在XML格式的文件中。

SharedPreferences接口常用的方法有：

|方法|说明|
|----|----|
|edit|建立一个SharedPreferences.Editor对象|
|contains|是否包含键值|
|getAll|返回所有配置信息|
|getBoolean|获得一个boolean数据|
|getFloat|获得一个float数据|
|getInt|获得一个int数据|
|getLong|获得一个long数据|
|getString|获得一个string数据|




#### 第4节  访问远程数据库


### 第9章  地图服务与传感器检测技术

#### 第1节  电子地图服务与应用程序开发

地图服务：采用高德开发者，见样例

#### 第2节  传感器检测技术

Android内部内置了很多类型的传感器，封装在Sensor类中，常见的传感器类型有：

|类型常量|说明|
|----|----|
|Sensor.TYPE_ACCELEROMETER|加速度传感器|
|Sensor.TYPE_LIGHT|光传感器|
|Sensor.TYPE_MAGNETIC_FIELD|磁场传感器|
|Sensor.TYPE_PROXIMITY|距离传感器|
|Sensor.TYPE_AMBIENT_TEMPERATURE|温度传感器|
|Sensor.TYPE_PRESSURE|压力传感器|
|Sensor.TYPE_ALL|所有类型传感器|

传感器管理类SensorManager：

Android中所有传感器都需要通过传感器管理类来访问，通过静态方法可以创建管理类对象。
|方法|说明|
|----|----|
|getSensorList|获取传感器类型列表|
|registerListener|注册传感器监听器|
|unregisterListener|注销传感器监听器|
|goDefaultSensor|获取默认传感器|

```java
// 枚举传感器类型

package com.example.myamap;

import androidx.appcompat.app.AppCompatActivity;
import android.hardware.Sensor;
import android.hardware.SensorEvent;
import android.hardware.SensorEventListener;
import android.hardware.SensorManager;
import android.os.Bundle;
import android.widget.LinearLayout;
import android.widget.TextView;

import java.util.List;

public class MainActivity extends AppCompatActivity implements SensorEventListener {

    private SensorManager manager;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    @Override
    protected void onResume() {
        super.onResume();
        manager = (SensorManager) this.getSystemService(SENSOR_SERVICE);
        List<Sensor> list = manager.getSensorList(Sensor.TYPE_ALL);
        LinearLayout layout = new LinearLayout(this);
        layout.setOrientation(LinearLayout.VERTICAL);
        TextView txt;
        for (Sensor s : list) {
            txt = new TextView(this);
            txt.setText(s.getName());
            layout.addView(txt, new LinearLayout.LayoutParams(
                    LinearLayout.LayoutParams.MATCH_PARENT,
                    LinearLayout.LayoutParams.WRAP_CONTENT
            ));
        }
        setContentView(layout);
    }

    @Override
    public void onSensorChanged(SensorEvent sensorEvent) {

    }

    @Override
    public void onAccuracyChanged(Sensor sensor, int i) {

    }
}

```






















