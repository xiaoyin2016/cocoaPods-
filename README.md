# cocoapods-
如何使用cocoapods来倒入第三方框架
具体步骤如下所示：
1.进入到项目的目录中: $ cd 目录 
2.使用终端命令行: $ vim Podfile 
3.然后按i键，进入编辑模式

platform :ios,'8.0'use_frameworks!
target '项目名称' do 
  pod 'AFNetworking', '~> 2.6' 
  pod '*****', '~> 3.0' end

4.编辑完后按下 esc 键，再按下:键 输入wq 保存。

导入框架
使用命令: $ pod install 
执行$ pod install 就都可以了。

5.如何解决头文件不显示的问题？
解决方式：打开项目，选择Target -> Build Settings 菜单，找到\”User Header Search Paths\”设置项
新增一个值"${SRCROOT}"，并且选择\”Recursive\”

6.CocoaPods常用命令

1、pod install
根据Podfile文件指定的内容，安装依赖库，如果有Podfile.lock文件而且对应的Podfile文件未被修改，则会根据Podfile.lock文件指定的版本安装。

每次更新了Podfile文件时，都需要重新执行该命令，以便重新安装Pods依赖库。

2、pod update
若果Podfile中指定的依赖库版本不是写死的，当对应的依赖库有了更新，无论有没有Podfile.lock文件都会去获取Podfile文件描述的允许获取到的最新依赖库版本。

3、pod search 库名
查找是否有第三方库, 以及该库的历史版本号。

