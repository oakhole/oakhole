---
  layout: post
  title: Mac OSX 使用Android Studio
  date: 2015-02-12 08:36:50
  category: 开发环境
---

Android Studio 集成了Intellij Idea ，也是我一直在使用作为java开发首选的IDE。

当前操作环境：osx 10.10.2，jdk 1.7

- 首先，进行下载安装[Android Studio]( http://www.android-studio.org)

- 安装顺利完成，打开后报错：

  <img src="{{basepath}}/img/2015-02-12/start-img.png">
  
  **解决方法：**
  
  检查当前环境jvm配置正确，打开安装路径下`plist.info`，修改如下键值：
  
      <key>JVMVersion</key>
      <string>1.6*,1.7+</string>
    
  > 1.0版本为`1.6*`，1.1 beta 版本则已修改为如上图所示。
    
- 顺利打开后一直停留在如下图所示无响应：
  
  <img src=" {{basepath}}/img/2015-02-12/login-img.jpg">

  **解决方法：**
  
  在安装路径`bin`路径下，修改`idea.properties`文件，末尾添加：
  
      disable.android.first.run=true
      
- 重新启动Android Studio 可打开至欢迎界面,选择新建项目时无响应：
  
  <img src="{{basepath}}/img/2015-02-12/welcome-img.png">
  
- 这里使用vpn进行组件下载，问题主要由于获取组件列表时问题，当开始下载时关掉vpn可正常使用本地网络下载，所以组件下载源没有被墙，只是在获取列表时出现问题，如下图为开启VPN后下载安装过程：

  <img src="{{basepath}}/img/2015-02-12/downloading-img.jpg">
  
- 待下载完成后，即可新建项目，或进行SDK manager 操作

  <img src="{{basepath}}/img/2015-02-12/newProject.png">
  
  <img src="{{basepath}}/img/2015-02-12/targetAndroidDevices.png">
  
  <img src="{{basepath}}/img/2015-02-12/addActivity.png">
  
  <img src="{{basepath}}/img/2015-02-12/customizeActivity.png">
  
  <img src="{{basepath}}/img/2015-02-12/buildingProject.png">
  
  <img src="{{basepath}}/img/2015-02-12/editor.png">
  
- 接下来就是一些调试运行blar blar blar ……
  
  <img src="{{basepath}}/img/2015-02-12/debug.png">

- 至此，mac下算是正常使用Android Studio进行android开发了，BTW，Idea vim plugin 不错

#### 结语

> 算是匆匆了结了该文，主要是我在安装过程中遇到的一些问题，至于安装完后的一些操作就可以参考官网进行操作了，如果有需要，可以一起共同学习交流，我之前因为一直将 idea 作为java web的IDE，且对Gradle有些许了解，就不作为赘述，官网有详细教程可供参考。