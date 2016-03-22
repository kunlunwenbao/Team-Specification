# 赛导游项目开发文档


## 一. App开发规范
#### 1.总则



## 2. 代码规范
***
###1.    总则
* 软件开发要及时提交git，每天根据安排修改及时push。push之前要先pull，**做到每次提交的代码都是可以运行的**

* 严格保证代码的可读性，做好看名字知功能，类名，函数名，变量名使用英文驼峰命名法。

* 所有的Defalut存储和通知所使用的字符串常量必须在宏定义中书写

* 不要将最常见的类如appdelegate，隐藏的太深，一般放在App文件夹里或者直接爆露在项目外

### 2. 关于命名
* 项目Group文件夹命名可以使用中文，如“首页”，代码文件要放在对应文件夹里，不要跨文件夹或者直接放在项目路径下

* 代码文件命名首字母必须大写，原则上以Group＋功能＋类型的命名准则。
如HomeVoicePlayModel ，如果文件包含的功能过多则可以使用类似“HomeViewController命名”，如果一个文件包含的代码超过300行，则要将非主要逻辑代码拆开放到工具类里面。

* 函数名命名 ：以 get、set 开头的方法有特殊的意义，不要随意定义。
set 是属性默认的设置方法，如果函数不是为了设置类成员，则不要用 set 开头，可用 setup 替代。
get 和属性方法无关，但在 Cocoa 中，其标准行为是通过引用传值，而不是直接返回结果的。欲获取变量，直接以变量名为名，如：userInfomation，而不是 getUserInfomation。

例如： 

// OK

  － (NSString *)name;

// 糟糕，应用上面的写法

－ (NSString *)getName;

// OK，但极少使用

－ (void)getName:(NSString **)buffer range:(NSRange)inRange;


// OK

－ (NSSize)cellSize;

// 糟糕，应用上面的写法

－ (NSSize)calcCellSize;


// 对 controller 做一般设置，OK

－ (void)setupController;

// 列出具体设置的内容，更好

－ (void)setupControllerObservers;

// 糟糕，set 专用于设置属性

－ (void)setController;

* 通知命名

	基本命名格式是：[与通知相关的类名] + [Did | Will] + [UniquePartOfName] + Notification，例：NSApplicationDidBecomeActiveNotification
NSWindowDidMiniaturizeNotification
NSTextViewDidChangeSelectionNotification
NSColorPanelColorDidChangeNotification

	名字要尽量的长来保证不重复，要是用全拼不要用缩写


* 临时变量
*推荐的前缀：

前缀 | 含义
-----|-----
ix   | 序号，起始为0
in   | 序号（自然数范围），起始为1
if   | 类型为浮点的“序号”
x    | 坐标
y    | 坐标
w    | 宽度
h    | 高度
vc   | 视图控制器
v    | 视图
