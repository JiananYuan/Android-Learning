# Android-learning

## 教程基于《Android Studio 应用程序设计（第2版）》 --张思民著

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


#### 第3节 文本编辑框EditText

继承自TextView

#### 第4节  Android布局管理

Andrid系统的布局管理指的是在XML布局文件中设置组件的大小、间据、排列及对齐方式等。
Android常见的布局方式有LinearLayout，FrameLayout，TableLayout，RelativeLayout，GridLayout

线性布局是所有布局中最常用的一种布局方式，要么水平线性布局，要么垂直线性布局

帧布局是将组件放置到左上角位置，当添加多个组件时后面的组件将遮盖之前的组件

表格布局是将页面划分成由行、列组成的单元格,列数由shrinkColumns定义，行由TableView标签定义

相对布局是采用相对其他组件位置的布局方式。在相对布局中通过指定id关联其他组件与之右对齐、上下对齐或以屏幕中央等方式来排列组件

网格布局是设置区域为若干行和若干列的网格


#### 






