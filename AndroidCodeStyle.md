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
* 图片命名,资源文件,控件id命名：activity名称+功能名称（背景bg，按钮bt,图片控件iv等）+自己名称<br />
* 控件命名：按钮bt_,图片控件iv_<br />
* Acitity,Fragment,Delegate,前缀全部一样<br />

### 3. 代码规范
* 所有逻辑相关的东西都在逻辑包之下，例如com.touchmedia.daolan<br />
* 一些项目整体相关的类，例如Application放在逻辑包com.touchmedia.daolan之下<br />
* UI相关，例如Activity放在逻辑包com.touchmedia.daolan.ui之下<br />
* Service相关，例如Service放在逻辑包com.touchmedia.daolan.service之下<br />
* 实体以及控制器Controller,每一个实体对应一个Controller,逻辑包com.touchmedia.daolan.model之下<br />
* 联网相关Task以及联网基础类以及联网实体类等放在,逻辑包com.touchmedia.daolan.cloudservice之下<br />
* 工具类联网基础类等相关的东西都在com.之下，包括http联网基础类，UI基础类，Utils工具类，View通用界面，与逻辑包处于平行的位置<br />
* AndroidManifest中的activity，service，权限等加上注释，名称用途等<br />
* 添加权限时仔细查看AndroidManifest表，防止重复添加
* HttpParameter类主要放置联网参数信息，每个参数必须加上注释增加程序可读性

