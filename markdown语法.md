# markdown语法

[toc]

---

> **注意：为保证成功注释，所有实例代买-->均被写成- ->**

## 格式设置

## 流程图（mermaid）

### 简单连接图（graph）

<!--
```mermaid
graph TB
    A[Apple]- ->B{Boy}
    A---C(Cat)
    B.->D((Dog))
    C==喵==>D
    style A fill:#2ff,fill-opacity:0.1,stroke:#faa,stroke-width:4px
    style D stroke:#000,stroke-width:8px;
    ```
 -->

- 语法结构
  >\```mermaid
  >graph 方向
  >节点以及节点连线（定义和连线步骤可以分开）
  >（样式调整）
  >\```

- 整体布局
  >TB 从上到下
  >BT 从下到上
  >RL 从右到左
  >LR 从左到右
  >TD 同TB

- 基本图形
  >id + [文字描述]矩形
  >id + (文字描述)圆角矩形
  >id + >文字描述]不对称的矩形
  >id + {文字描述}菱形
  >id + ((文字描述))圆形
  
- 连接图线条设置
  >A --> B     A带箭头指向B
  >A --- B      A不带箭头指向B
  >A -.- B      A用虚线指向B
  >A -.-> B    A用带箭头的虚线指向B
  >A ==> B   A用加粗的箭头指向B
  >A -- 描述 --- B       A不带箭头指向B并在中间加上文字描述
  >A -- 描述 --> B      A带箭头指向B并在中间加上文字描述
  >A -. 描述 .-> B      A用带箭头的虚线指向B并在中间加上文字描述
  >A == 描述 ==> B  A用加粗的箭头指向B并在中间加上文字描述

- 自定义样式
  >语法：style id 具体样式
  >自用：style A fill:#FFFF66,fill-opacity:0.1,stroke:#3399FF,stroke-width:2px
  >- **设置默认样式**
  >classDef node fill:#FFFF66,stroke:#3399FF,stroke-width:3px

#### 子程图

- 用法
  >subprocess id
  
<!--mermaid
graph TB
    c1- ->a2
    subgraph one
    a1- ->a2
    end
    subgraph two
    b1- ->b2
    end
    subgraph three
    c1- ->c2
    end
  -->

---



### 流程图（flowchart）

<!-- ```mermaid
	flowchat
	st=>start: 开始
	e=>end: 结束
	op1=>operation: 操作1 | past
	op2=>operation: 操作2 | current
	op3=>operation: 操作3 | future
	pa=>parallel: 多输出操作4 | approved
	cond=>condition: 确认？ | rejected
	
	st->op1->cond
	cond(true)->e	
	cond(no)->op2(right)->op3->pa(path1,right)->op1
	pa(path2,left) ->e
	st@>op1({"stroke":"Blue"})@>cond({"stroke":"Green"})@>e({"stroke":"Red","stroke-width":6,"arrow-end":"classic-wide-long"})
	``` -->

- 语法结构
  > \```mermaid
  >flowchat
  >定义节点
  >连接节点
  >样式调整）
  >\```

- 节点定义
  >变量名=>节点标识: 节点显示名

- 节点连线
  >变量名1->变量名2->...->变量名n
- 节点类型
  >开始（椭圆形）：start
  >结束（椭圆形）：end
  >操作（矩形）：operation
  >多输出操作（矩形）：parallel
  >条件判断（菱形）：condition
  >输入输出（平行四边形）：inputoutput
  >预处理/子程序（圣旨形）：subroutine
  
- 连线样式
  >变量名@>变量名n({"key":"value"})

- 关键字
  >  yes/true：condition类型变量连接时，用于分别表示yes条件的流向
  >no/false：同上，表示否定条件的流向
  >left/right：表示连线出口在节点位置（默认下面是出口，如op3），可 以 跟condition变量一起用：cond(yes,right)
  >path1/path2/path3：parallel变量的三个出口路径（默认下面是出口）
- 节点状态
  >为节点设置不同的状态，可以通过不同的颜色显示，其中状态包括下面6  个，含义如英文所示，
  >- past
  >- current
  >- future
  >- approved
  >- rejected
  >- invalid

### 时序图（sequenceDiagram）

<!-- ```mermaid
    sequenceDiagram
    participant 张 as 张三
    participant 李 as 李四
    participant 王 as  王五
    张 ->> +李: 你好！李四, 最近怎么样?
    李- ->> 王: 你最近怎么样，王五？
    李--x -张: 我很好，谢谢!
    activate 王
    李-x 王: 我很好，谢谢!
    Note over 李,王: 李四想了很长时间, 文字太长了<br/>不适  放在一行.
    deactivate 王
    loop 李四再想想
    李- ->>王: 我还要想想
    王- ->>李: 想想吧
    end
    李- ->>张: 打量着王五...
    张->>王: 很好... 王五, 你怎么样?
```
 -->

- 语法结构

  >\```mermaid
  >sequenceDiagram
  >participant 别名 as 对象显示名（全部直接用显示名时可以不写）
  >顺序增加图表中消息
  >（可以加入标签提示）
  >\```

- 消息格式
  > 【对象1】【箭头类型】【对象2】 : 消息内容

- 连接样式
  >实线：->
  >虚线：- ->
  >带箭头的实线：->>
  >带箭头的虚线：- ->>
  >带x的实线：-x
  >带x的虚线：- -x

- 激活方块
  > 这部分有两种写法，第一种是显示通过语法实现，语法如下，会在指定对象的消息中增加，示例中李四；第二种直接在对象前面增加加减号（开始时用加号“+”，结束时用减号“-”），则在加号对应的对象上开始，减号对应的时间结束，示例中王五。
  >*开始：activate 【对象】*
  >*结束：deactivate 【对象】*

- 注释
  > **Note 【位置】 【对象】**
  >注释显示的位置有三个，以被标记的对象中心为参考系，基于横跨多个时，可以都逗号分隔，如示例：
  >*right of*
  >*left of*
  >*over*

- 循环
  loop 循环说明
【消息流】
end

- 条件（if/else）
  >alt 条件说明
  >【消息流】
  >else
  >【消息流】
  >end
  >opt 条件说明
  >【消息流】
  >end

<!-- 
```mermaid
	    sequenceDiagram
	    participant 张 as 张三
	    participant 李 as 李四
	    张 ->> 李: 你好！李四, 最近怎么样?
	    alt 如果感冒了
	    李->> 张: 不太好，生病了。
	    else 挺好的
	    李->> 张: 我很好，谢谢。
	    end
	        opt 另外补充
	        李->> 张: 谢谢问候。
	    end
	```
 
 -->

### 甘特图

<!-- 
```mermaid
gantt
    title A Gantt Diagram
    dateFormat  YYYY-MM-DD
    section Section
    A task           :a1, 2014-01-01, 30d
    Another task     :after a1  , 20d
    section Another
    Task in sec      :2014-01-12  , 12d
    another task      : 24d
    ```
 -->

## 流程图简单版本（flow）

- 定位元素语法
  >tag=>type: content:>url

<!-- 
```flow
 st=>start: 开始
 e=>end: 结束
 op=>operation: 操作
 sub1=>subroutine: 子程序
 cond=>condition: Yes or No?
 io=>inputoutput: 输入/输出
 st->op->cond
 cond(yes)->io->e
 cond(no)->sub1(right)->op
 ```
 -->

- 说明
  >- tag 是流程图中的标签，在第二段连接元素时会用到。名称可以任意，一般为流程的英文缩写和数字的组合。
  >- type 用来确定标签的类型，=>后面表示类型。由于标签的名称可以任意指定，所以要依赖type来确定标签的类型
  >标签有6种类型：start end operation condition inputoutput subroutine
  >- content 是流程图文本框中的描述内容，: 后面表示内容，中英文均可。特别注意，冒号与文本之间一定要有个空格
  >- url是一个连接，与框框中的文本相绑定，:>后面就是对应的 url 链接，点击文本时可以通过链接跳转到 url 指定页面
  >**1. 开始**
  >*st=>start: 开始*
  >**2. 结束**
  >*e=>end: 结束*
  >**. 操作**
  >*op1=>operation: 操作、执行说明*
  >**4. 条件**
  >*cond=>condition: 确认？*
  >**5. 输入输出**
  >*io=>inputoutput: catchsomething...*
  >**6. 子程序**
  >*sub1=>subroutine: My Subroutine*
  >**7. URL**
  >*e=>点击本结束跳转:>https://www.baidu.com*

- 连接元素语法
  >使用 -> 来连接两个元素
  >对于condition类型，有yes和no两个分支，如示例中的cond(yes)和cond(no)
  >每个元素可以制定分支走向，默认向下，也可以用right指向右边，如示例中sub1(right)。

<!-- ```flow
st=>start: 生产者线程进入 :>https://blog.csdn.net/qq_21808961
op1=>operation: 设置Info类的名称和内容
op2=>operation: 修改标志位
op3=>operation: 等待线程唤醒
op4=>operation: 等待消费者取走
cond=>condition: 判断标志位

st(right)->cond->op1->op2->op3
cond(yes,right)->op1
cond(no)->op4
``` 
-->
<!-- 上面的流程图使用了URL点击上面的的开始框(生产者线程进入)，就会跳转到我的博客首页。 
这里再强调一下：每一个元素都可以加上right指明流程流程图的方向，如果不指定的话默认是向下的 -->
