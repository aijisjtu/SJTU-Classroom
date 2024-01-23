# ICE2604-001

## 写在前面

框架： vue3   [教程在这](https://www.runoob.com/vue2/vue-tutorial.html)

版本信息：![输入图片说明](vue%E7%89%88%E6%9C%AC%E4%BF%A1%E6%81%AF.png)

IDE： 推荐大家使用jetbrains系列的IDE，可以在交大软件授权中心获取～ 
vue开发的话可以用webstorm，python可以用pycharm。因为它是集成的，环境管理会做的很好，相对于vscode会更安全一点，可以省去很多不必要的麻烦，比如它可以在创建项目时直接为你提供vue选项，不用动手配置，还是很爽的。当然vscode也有它的优点，大家各取所需吧～

 :pencil2: `PLUS` 指当前阶段暂不要求的功能，且做锦上添花。

 :bowtie: 

## Parts Infos

## 网页UI设计

### 参考网站

米哈游 https://www.mihoyo.com/

交大图书馆 http://xgh.lib.sjtu.edu.cn/#/login （动态背景）

### 工具

- Figma

### 数据库

#### 教程相关
本意是希望能够让大家轻松共用一个数据库，但我早上查了查资料发现，基本只能局限于一个局域网内的交流，否则需要部署到云服务上（花钱）。 
**负责数据库的uu感兴趣的话可以搜索下相关资料尝试下**，或者到时候答疑的时候可以问问～

Navicat设置用户权限：https://blog.csdn.net/qq_21187515/article/details/92618885

### 爬取网站

图书馆座位预约系统： https://libseat.lib.sjtu.edu.cn/#/ic/home

自习室座位实时信息： https://ids.sjtu.edu.cn/build/goMRealtimeDynamic?param=cd6b63cb06a935de3050b73a4c68c87f0a78ca628b777157b4cc6cd3efd55b3e

#### 数据获取部分任务

1. 从网站上爬取所需信息（见下）。并将信息导入到本地数据库。   :pencil2:`PLUS: 实现间隔一段时间自动爬取数据并更新数据库的脚本`
2. 将数据库中的数据部署到API以供访问（FastAPI + pymysql）。
3. 检查返回数据是否符合要求。

#### 数据文件格式

对于一间教室，目前需要获取的相关数据为：
| 数据含义      | 字段名       | 数据类型   |
|-----------|-----------|--------|
| 教室名       | classroom | string |
| 教室当前空余人数  | vacancy   | num    |
| 教室可容纳人数   | capacity  | num    |
| 教室详细介绍的链接 | detailUrl | string |

 **最重要的一点是** 对于教室我们首先要知道它 _当前是否有排课_ ！这个需要在两个网站中跳转，具体处理就交给负责爬虫的同学了🧑‍🎓 


咱们写爬虫的时候可以让爬虫爬几个就写入数据库，然后让图表动态更新，这可以一定程度上解决爬虫速度慢，数据不实时的问题


### 搜索部分

- 如果爬取了教室的信息界面，可以做一个教室信息的筛选界面（不是输入搜索，而是选项搜索）




### 可视化部分

Vue3 加载 Echarts：https://juejin.cn/post/6931988634874675213

Echarts教程：https://www.runoob.com/echarts/echarts-tutorial.html

#### 灵感

- [echarts时钟](https://echarts.apache.org/examples/zh/editor.html?c=gauge-clock) 可以直接嵌入到网站上

- [echarts日历热力图](https://echarts.apache.org/examples/zh/editor.html?c=calendar-heatmap) 可以用不同于折线图的方式展现数据

- [echarts磁盘分配图](https://echarts.apache.org/examples/zh/editor.html?c=treemap-disk) 可以用来展现当前人数多寡（但气泡图显然好看点）

- [echarts气泡图](https://echarts.apache.org/examples/zh/editor.html?c=circle-packing-with-d3) 用不同气泡大小展现当前房间的空余位置数，数越多，气泡越大

- [气泡图美化教程](http://blog.csdn.net/m0_67401851/article/details/123251878) echarts上的气泡图还要进行一些必要的修改才行！


#### 一些BUG

##### vue3

- 解决vue3引入jquery导致‘$‘ is not defined no-undef：https://blog.csdn.net/baidu_41617294/article/details/121029280
- 解决Element库中tagPage切换无效问题 https://www.cnblogs.com/hj0711/p/12166930.html
- 父子组件传参 https://www.cnblogs.com/GoodMemoryBlog/p/14192135.html
- vue data部分向echarts内部传递函数时无法有效访问：https://blog.csdn.net/liusa825983081/article/details/124321160


## 其他知识
### JavaScript
菜鸟教程：https://www.runoob.com/jsref/jsref-tutorial.html
- 函数前面加 ‘+’ 的作用 ：https://www.pipipi.net/2624.html

