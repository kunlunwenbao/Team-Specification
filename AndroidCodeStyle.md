< [Back](README.md)
## 一. App开发规范
#### 1.总则
#### 2. 命名规范
#### 2. 代码规范
***
###1.    总则
* 软件开发要及时提交git，每天根据安排修改及时push。push之前要先pull，**做到每次提交的代码都是可以运行的**

* 严格保证代码的可读性，做到看名字知功能，类名，函数名，变量名使用英文驼峰命名法。

### 2. 命名规范
* 项目名称首字母大写<br />
* Acitity,Fragment,类，首字母大写<br />
* 图片命名,资源文件命名：activity名称+功能名称（背景bg，按钮bt,图片控件iv等）+自己名称<br />
* 控件命名：按钮bt_,图片控件iv_<br />
* Acitity,Fragment,Delegate,前缀全部一样<br />

### 3. 代码规范1
* 所有逻辑相关的东西都在逻辑包之下，例如com.touchmedia.daolan<br />
* 工具类联网基础类等相关的东西都在com.之下，与逻辑包处于平行的位置<br />
* AndroidManifest中的activity，service，权限等加上注释，名称用途等<br />
* 添加权限时仔细查看AndroidManifest表，防止重复添加

