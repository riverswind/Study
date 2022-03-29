# 介绍
*本篇参考https://blog.csdn.net/yanbober/article/details/49314255，自己再整理，用于熟悉整理流程*

# gradle dsl基础
gradle本质就是个配置脚本，执行一种类型的配置脚本时就会创建一个关联的对象
脚本类型 | 关联对象类型|对应脚本
---|---|---
Build script| Project|比如Build.gradle
Init script|Gradle|对应USER_HOME/.gradle/.../init.d/目录下脚本
Settings script| Settings|settings.gradle


* Project对象：每个build.gradle会转换成一个Project对象。
* Gradle对象：构建初始化时创建，整个构建执行过程中只有这么一个对象，一般很少去修改这个默认配置脚本。
* Settings对象：每个settings.gradle会转换成一个Settings对象。

## Build script
每个工程的build.gradle对应一个Project对象.1个项目在构建时都具备如下流程：

1. 为当前项目创建一个Settings类型的实例。
2. 如果当前项目存在settings.gradle文件，则通过该文件配置刚才创建的Settings实例。
3. 通过Settings实例的配置创建项目层级结构的Project对象实例。
4. 最后通过上面创建的项目层级结构Project对象实例去执行每个Project对应的build.gradle脚本


## Init Script 
这种脚本在构建开始时执行。一般做全局的公共功能的监听器，或者日志管理。
脚本都是放在USER_HOME/.gradle/.../init.d/目录下脚本
参考文档：https://docs.gradle.org/current/userguide/init_scripts.html
![image](./assets/../../app打包基础/assets/init%20gradle.png)

## Settings Script
Settings实例与settings.gradle文件一一对应，它用来进行一些项目设置的配置。这个文件一般放置在工程的根目录。

## 生命周期
![image](./assets/../../app打包基础/assets/gradle%E6%B5%81%E7%A8%8B.png)

原文链接：https://blog.csdn.net/yanbober/article/details/49314255