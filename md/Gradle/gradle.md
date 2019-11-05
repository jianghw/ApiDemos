## 1. 命令

#### 1.1 创建

mkdir file_name
cd file_name
* gradle init
(使用Kotlin DSL使用gradle init --dsl kotlin)

* ./gradlew tasks
**win:** gradlew tasks
tasks命令列出可以调用的Gradle任务，包括base插件添加的任务，及添加的自定义任务


#### 1.2 分析和调试

* ./gradlew hw_zip --scan
* gradlew build --scan
--scan选项或将构建扫描插件明确应用于您的项目

* gradlew properties
 扫描信息：scans.gradle.com

* 强刷新
./gradlew --refresh-dependencies assemble

## 语义化
* major.minor.patch
    * 不兼容API变化，major增加
    * 兼容方式添加功能，minor增加
    * bug，patch增加


## 构建

初始化
配置
执行


## 2. Groovy
#### 2.1
#### 2.2
#### 2.3

## 3. Gradle
#### 3.1 Setting
#### 3.2 Build
#### 3.4 Project
#### 3.5 依赖
* 更广泛的作用域，跨Project，跨Task
* 可以应用于SourceSet
#### 3.6 API
#### 3.7 自定义属性
#### 3.8 脚本

## 4. Gradle Task
#### 4.1 创建
#### 4.2 访问
#### 4.3 分组与描述
#### 4.4 操作符
#### 4.5 执行分析
#### 4.6 排序执行
#### 4.7 启用与禁用
#### 4.8 onlyIf
#### 4.9 任务规则
