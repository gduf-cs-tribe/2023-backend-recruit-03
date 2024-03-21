# 2023-backend-recruit-03-Level3

# **考核说明-呱呱学术管家**

# 目录

**本考核内容针对学习java的同学设计**



## **项目介绍（场景介绍）**

​		小爪是一名大学生，出于对编程的热爱，选择了计算机专业。小爪上了大学，一直热衷于学习，钻研书籍。所以，到了大一学期下半年，小爪就已经学习大部分技术。但是令小爪头痛的是：学了很多技术但是却没有用武之地，小爪因为是自学且领先了别人一大步，所以它不知道有哪些项目比较适合拿来练手。这个时候，小爪突然想到了前几天为了给下学期选则选修课的教务系统。小爪一直很好奇：为什么教务系统每到选课的时候基本上登不上去，然后是如何保证选课安全的问题。这个时候，小爪的头脑里突然萌生了很多想法：想要实现很多模块（管理员、教师、学生）等有关角色模块.....，但是，小爪发现自己的重点都是在软件设计的学习，而对于代码的具体实现却没有深入。小爪也不灰心，想着把核心功能和一些伴随功能可以实现的前提下，并添加自己的创意（不会脱离教务系统的定义）,并寻找一位可以信任的小伙伴来帮助小爪一起开发，你会是小爪的伙伴吗?

 

为小爪使用代码实现一个web环境下的教务系统，并且利用Java原生API、JavaWeb等知识，完成以下要求：



## **涉及技术关键字**

1. JavaSE相关知识（接口、抽象类、异常处理、多线程等..）
2. JavaWeb
3. Tomcat
4. 一些前端语言的基本使用（如：HTML、CSS、...）
5. SQL（采用MYSQL数据库）

## **角色要求**

| 管理员 | 一般为该系统的负责人员担任，负责教师信息的添加、修改、删除、查询等 |
| ------ | ------------------------------------------------------------ |
| 教师   | 负责讲授课程的教师，一般负责添加课程信息、修改课程信息、设置分数比重... |
| 学生   | 该系统的主要用户，一般只具备读功能                           |

 

## **业务功能要求**

### 一. **基本内容及功能**

#### 1. 登录功能

##### **1.1管理员登录**

\> 介于减少开发的代码量，当前项目下，允许管理员、教师、学生等共用一个登录页面

\> ***\*建议\****：当前系统下可以在创建数据库的时候就创建一个允许使用的管理员账号

\> ***\*最低要求\****：实现最基本的账号验证、密码校验要求、密码隐藏\显示

\> ***\*拓展功能参考\****：白、黑名单IP地址设置、本机信任登录(可以模拟SSH的验证方式)、...

\> ***\*参考图片\****：图片仅供参考，有自己的想法按照自己的想法

 

![](https://pic.imgdb.cn/item/65fab7a49f345e8d03b47ade.png) 

 

 

##### **1.2教师&学生登录**

\> 介于减少开发的代码量，当前项目下，允许管理员、教师、学生等共用一个登录页面

\> ***\*注意事项\****：介于教务系统的特殊性，所有账号非管理员用户无法手动创建，而是由后台同一生成分配

\> ***\*最低要求\****：实现最基本的账号验证、密码校验要求

\> ***\*拓展功能参考\****：图片验证码、数字验证码、三天/七天免登录...

 

 

 

#### 2. **管理员功能**

\> 小爪想体验一下超管的至高无上的权力，于是特地想让你实现一下这个功能，不过不实现也没有关系，小爪也就只会伤心一下而已啦

\> ***\*角色作用\****：一般是为了管理教务系统所有非管理员账号的添加、删除、查询、管理

\> ***\*注意事项\****：这里的账号管理非账号详细信息的管理，而是针对于账号和口令的管理

\> ***\*建议\****：该模块功能为可选功能，是否实现该功能取决于对于该项目的规划和时间安排

 

##### **2.1添加教师账号**

\> 教师账号格式推荐 ： 届号（2位） + 院系号（3位）+ 添加顺序（4位）（第一个添加的话为0001）

\> ***\*建议\****：当前系统下可以在创建数据库的时候就创建一个允许使用的管理员账号

\> ***\*最低要求\****：实现最基本的单个账号添加、并所作的CRUD操作可以同步到数据库下并发挥作用

\> ***\*拓展功能参考\****：批量添加、密码随机生成、规则生成(按照某种规则生成多个符合该规则的账号)、过滤机制（按照某种规则排除部分特殊的账号）、密码统一设置、

根据提供的教师资料文件实现账号绑定、***\*教师文件上传（加分项，参考下述）\****

\> ***\*解释\****

1. 批量添加：提高效率，搭配规则生成和过滤机制一起使用
2. 密码随机生成：解放管理员的双手，一般为强密码类型，不过后续可以根据密码统一设置设置弱密码类型
3. 规则生成：常见的有：范围生成、前缀生成、无序生成..
4. 过滤机制：为了迎合学校教师号(类似于学号)的一些特殊规则

\> ***\*图片参考\****：基于范围生成规则、多场景筛选机制

 

参考例子详细解答

**1.** ***\*最小值&最大值\****：格式：整数值（4位，最大支持0000~9999，不考虑额外情况），针对对象为添加顺序（届号和院系号不能指定）

**2.** ***\*随机密码生成\****：二选一，每一个教师账号拥有不同的密码，且是随机的，强类型密码

**3.** ***\*统一密码生成\****：二选一，每一个教师账号拥有相同的密码，一般为弱类型密码

**4.** ***\*届号\****：查询数据字典表获取到自动切换的届号，可以很好表示教师入职的时间

**5.** ***\*密码设置\****：该项在”统一密码生成”功能下才会生效

**6.** ***\*教师文件上传（可选功能项）\****：根据上传的教师文件，可以实现账号绑定；需要考虑下述问题

(1) 最大值 - 最小值 > 教师信息文件记录数量 或 最大值 - 最小值 < 教师信息文件记录数量

(2) 由于有记录身份证，所以同一个身份证号的教师是否可以拥有两个教师号?

(3) 文件格式编码，采取最为合适的编码格式（UTF-8,GBK...）

(4) 文件格式语法校验

(5) 是否支持一次性选择多个文件呢?

(6) 根据文件中的院系名称匹配或精准查询院系号（如互金院可以查询出来、互联网金融与信息工程学院也可以查询院系号）

(7) 文件下的院系名称查询不到院系号，如何处理?

![](https://pic.imgdb.cn/item/65fab7f39f345e8d03b601c1.png) 

![](https://pic.imgdb.cn/item/65fab7fe9f345e8d03b637dd.png) 

 

点击详情展示信息大致如下：

![](https://pic.imgdb.cn/item/65fab8139f345e8d03b69db8.png) 

##### **2.2添加学生账号**

\> ***\*建议\****：学生账号格式为：届号(2位) + 院系号(3位) + 专业号(2位) + 班级号（1~2位) + 添加顺序(0 ~ 100，不会出现有的班级有100人吧，都大学了^^)

\> ***\*最低要求\****：实现最基本的单个账号添加、并所作的CRUD操作可以同步到数据库下并发挥作用

\> ***\*拓展功能\****：批量添加、密码随机生成、规则生成(按照某种规则生成多个符合该规则的账号)、过滤机制（按照某种规则排除部分特殊的账号）、密码统一设置、

***\*根据提供的学生资料文件实现账号绑定学生文件上传（加分项，参考下述）\****

\> ***\*提供参考\****

***\*> 配置项介绍\****

**1.** ***\*最大值&最小值：\****整数值，范围为(0~99)，只针对添加顺序

**2.** ***\*随机密码上传\****：同“添加教师账号”同名项定义

**3.** ***\*统一密码上传\****：同“添加教师账号”同名项定义

**4.** ***\*密码设置\****：同”添加教师账号”同名项定义

**5.** ***\*届号：\****同“添加教师账号”同名项定义

**6.** ***\*文件上传（可选）\****：文件内容自定义匹配规则

(1) 若不选择文件上传格式，则可选必须改为必选的

(2) 若选择文件格式，可以在生成过程中不填写可选选型，可选特性是为了解决开学途中有教师入职的

(3) 可选特性下，院系好和专业号必须同时有值；优先级高于文件

(4) 班级个数可以选择可以不选择，如果不选，介于文件记录数量来分配班级

(5) 院系号和专业号不能使用填写的方式，只能使用下拉列表的形式

(6) 当院系号选择了，专业号的可选项会根据院系号的变化而变化

(7) 如果没有选择院系号，则专业号默认展示全部

(8) ...

 

![](https://pic.imgdb.cn/item/65fab8219f345e8d03b6e098.png) 

![](https://pic.imgdb.cn/item/65fab82c9f345e8d03b71457.png) 

 

点击“详情”功能键后大致如下

![](https://pic.imgdb.cn/item/65fab8389f345e8d03b74a00.png) 

##### **2.3修改账号信息**

\> ***\*注意\****：管理员修改的账号信息不是账号的详细信息，而是账号、口令、是否异常、是否封禁，账号一般生成后特殊情况下不会发生更改

\> ***\*最低要求：\****能够单个修改密码、批量修改密码，能够修改异常标志、能够修改封禁信息

\> ***\*扩展功能：\****异常账号的定时检测(如何才算是一个异常账号、黑客绕过程序添加、或基于网络延迟而导致系统bug?)

\> ***\*特点：\****异常账号用户登录会受到异常账号警告；封禁账号无法登录

如果是教师账号会限制权限，如果是学生账号仍然只有读操作

\> ***\*所解决的问题\****：避免一些非法课程的创建、非法信息的发布等问题

\> 异常教师账号会限制权限

![](https://pic.imgdb.cn/item/65fab8439f345e8d03b777ac.png) 

 

\> 当学生账号异常 无论是否在线还是重新登录 都会显示异常通知信息

![](https://pic.imgdb.cn/item/65fab84f9f345e8d03b7a9d2.png) 

\> 当教师账号异常，也会限制权限，都会显示异常通知信息

![](https://pic.imgdb.cn/item/65fab8589f345e8d03b7cb97.png) 

##### **2.4删除账号信息**

\> ***\*注意\****：该删除行为的执行频率会非常低，一般情况下不会进行删除

\> ***\*最低要求：\****删除正常账号会有提示、可以删除异常账号和封禁账号、批量删除、是否删除验证

\> ***\*扩展功能：\****删除长期旧账号、筛选非法账号(凡是非法请求创建的账号)，执行删除

\> ***\*所解决的问题\****：释放服务器存储空间、避免非法账号登录，提高可靠性，降低风险

询问是否执行删除操作

\> ***\*建议\****：删除账号信息建议是逻辑删除，而不是真正物理删除，避免误判

![](https://pic.imgdb.cn/item/65fab86f9f345e8d03b8280b.png) 

##### **2.5查询账号信息**

\> ***\*触发条件\****：点击”详情”按钮展示出有关账号信息

\> ***\*可以展示的账号信息：\****账号，后2位显示的密码，账号头像(生成时会默认有一张头像),创建账户时间、修改账户密码时间、封禁状态、异常状态、...、所属专业、姓名、学号/教师号...

​	

\> 该图为详细信息的一部分，相关信息跟当前账号是`学生号`还是`教师号`有关

例：教师号不会有专业 但是会有院系等信息（拓展），学生号有专业、学号等信息

![](https://pic.imgdb.cn/item/65fab87b9f345e8d03b85d71.png) 

![](https://pic.imgdb.cn/item/65fab8389f345e8d03b74a00.png) 

##### **2.6制定院系号**

\> ***\*描述\****：每一个院系都有一个唯一标识

\> ***\*基本功能\****：添加院系、且院系的添加操作可以持久化到数据库、打开详情页、删除

\> ***\*扩展功能\****：该项院只要求添加即可，不考虑实际开发环境下一些极端情况

\> ***\*建议\****：不需要过多的记录，只需要有1~3院系即可 可以自行扩展

\> ***\*注意\****：详情页自行实现，建议：里面涉及到专业的一些基本信息、人数等

 

![](https://pic.imgdb.cn/item/65fab88f9f345e8d03b8b4ed.png) 

 

 

\> 点击“添加”图标来添加的新的院系号

![](https://pic.imgdb.cn/item/65fab8979f345e8d03b8dc0a.png) 

##### **2.7制定专业号**

\> ***\*描述\****：每一个院系下有多个专业好，每一个专业号都有一个唯一标识

\> ***\*基本功能\****：根据外键约束添加专业(自己判断)

\> ***\*扩展功能\****：该项只要求添加，不考虑实际开发环境下一些极端情况

\> ***\*注意\****：禁止出现非法专业号(不属于任何院系的专业号)

\> ***\*建议\****：添加专业号不需要太多的实例，只需要有5~10个测试案例即可，1个院系至少1个

 

\> 下述图片仅供参考，可以根据自己想法扩展字段列

![](https://pic.imgdb.cn/item/65fab8a39f345e8d03b91549.png) 

\> 添加专业可以查看上述“制定院系号”的流程

\> 详情信息自己实现，不提供样例

##### **2.8管理当前届**

\> ***\*描述\****：教务系统会使用一个值来记录届号（例如之前是22届，现在新生就是23届）

\> ***\*作用\****：届号作为学号的前缀（如：22届的 ： 22xxxxxxx）

\> ***\*建议\****：建议创建一个数据字典表，可以记录一些不需要构成表结构的单实例数值

\> ***\*基本功能\****：添加届号、根据日期来自动切换届号

\> ***\*要求\****：为了能够看到自动切换的效果，在提交项目前将切换间隔切换为1分钟，便于观看

\> ***\*拓展功能\****：可以自行扩展

##### **2.9教师账号权限分配**

\> ***\*描述\****：教师账号不是一定就能CRUD课程信息，分配的权限是弱类型权限

\> ***\*流程\****：添加、修改、删除课程申请 -> 申请通过 -> 真正持久化到数据库下

\> ***\*权限分类\****：是否允许特定查询、是否允许全部查询、是否允许修改、新增、删除（全局/制定）

\> ***\*功能键所在位置\****：教师账号详情页面的正上方“权限分配”功能项（下述为权限分配面板）

![](https://pic.imgdb.cn/item/65fab8bc9f345e8d03b9838a.png) 

 

##### **2.10权限申请**

\> ***\*描述\****：当某一个教师对某一个课程具备状态更改需求的时候，会向管理员申请权限

\> ***\*注意\****：一旦同意其申请，仍然是弱类型的权限，管理员在当前模块下管理申请请求

\> ***\*最低功能\****：可以查看教师发出的申请请求，可以许可/拒绝申请请求

\> ***\*拓展功能\****：不做要求，时间充足的可自行扩展

\> 案例演示：可以参考下述或自行扩展，在拒绝申请的时候需要填写申请理由

![](https://pic.imgdb.cn/item/65fab8c49f345e8d03b9ac5b.png) 

##### **2.11课程状态更改申请**

\> ***\*描述\****：当教师修改、创建课程需要将资料通过系统发给管理员进行审核

\> ***\*课程状态\****：已提交  审核通过 审核不通过 公开 隐藏

\> ***\*注意\****：当课程未审核通过，是不能持久化到审核通过的数据库的，需要存放到预备数据库下

\> demo解释

1. 教师号：需要执行的行为
2. 行为：创建还是修改
3. 操作对象：课程名称，课程号和课程名称构成主键
4. 账号状态：异常还是正常，异常不会通过的
5. 提交资料：一般为修改申请资料、创建申请资料
6. 其余操作：根据后面的给出的字体图标自己扩展（···表示可以查询提交的课程信息）

![](https://pic.imgdb.cn/item/65fab8cf9f345e8d03b9da88.png) 

 

##### **2.12班级管理**

\> ***\*描述\****：在根据文件产生学生账号的时候，会根据提供的院系号、专业号生成班级

\> ***\*带有属性\****：班级号，专业，几班，人数

\> ***\*班级号的构成\****：届号（2位） + 院系号（3位） + 专业号（2位） + 班次（1、2、3、4）构成班级号，（如22届的互金院的计算机科学与技术4班： 22001011）

\> ***\*demo案例\****：不展示demo

#### 3. **教师功能**

所分配的权限是C、U、S，但C、U权限是弱权限，需要经过管理员同意之后权限才可以生效

默认情况下教务系统生成职工账号所分配的默认权限是R（检索）

 

##### **3.1添加课程信息**

\> ***\*描述：\****教师添加课程信息，属于一个申请新增课程的操作， 需要由管理员(教务职工人员)同意后凡可真正实现添加操作

***\*> 流程：\****添加 -> 申请 -> 同意 -> 持久化到公开数据库(学生可以访问到的数据库)

***\*> 基本功能：\****添加课程信息、等待申请结果、展示申请状态（已提交、审核通过、审核不合格、公开）

***\*> 拓展功能：\****允许提交申请资料(图片、文件)、...

\> ***\*忽略场景\****：不考虑同一门课程允许多个老师使用；即每一个老师会有属于自己的课程记录

\> ***\*触发行为：\****在教师管理界面的”课程管理”模块有允许添加的功能项

\> 课程管理下的***\*个人课程查询展示列表\****

1. 教师查询权限：特定查询、全局查询、是否两者都支持
2. 状态：参考下述（可自行扩展）

![](https://pic.imgdb.cn/item/65fab8da9f345e8d03ba12ab.png) 

\> 点击添加按钮展示的参考模板：附带下述填写项配置

**1.** ***\*课程名\****：倘若权限为指定创建的话，只能创建管理员允许其添加的课程名

**2.** ***\*适用人群\****：课程的适用范围，基础就是一般不需要前置知识，便于在大一、大二期间优先生成课表；进阶的话，一般会在大二、大三期间优先生成课表

**3.** ***\*前置课程\****：部分课程需要前置课程来支撑（如：javaEE的学习需要JavaWeb、JavaSE）

**4.** ***\*申请原因\****（加分）：该项可以提高申请通过的概率，可以传入图片、文字描述、链接

**5.** ***\*是否公开\****：该课程是否一旦申请通过，就可以供学生选择；若选择隐藏，则不会存储到公开池下

**6.** ***\*课程所属\****：属于哪一个学院开办的课程，便于课表生成

**7.** ***\*适用专业\****：该课程的专业适用范围，便于课表生成

**8.** ***\*课程性质\****：必修会在课表当中参与；选修的话会在选课管理模块发挥作用

**9.** ***\*选修分类\****：便于统计学分获取

10. ***左上角的”权限”***：指定创建“：可以是：仅查询、指定创建、全局创建

![](https://pic.imgdb.cn/item/65fab8e59f345e8d03ba4630.png) 

##### **3.2修改&查询指定课程信息**

\> ***\*描述\****：> ***\*注意\****：修改课程信息需要提交修改的详细信息和原因，经由管理员同意后方可持久化公开数据库

\> ***\*最低功能：\****修改课程信息、等待申请结果、显示申请状态(审核通过、审核未通过、已提交)

\> ***\*拓展功能：\****允许多格式提交修改资料的原因(文本、图片、文件)

\> ***\*触发时机\****：在展示列表的每一行记录的”详情“功能项触发

\> 案例demo：跟“添加功能”的案例较为相似，新增属性项：

1. 审核状态：若是审核不合格，需要有为什么审核没有通过的原因，其余状态自行安	排
2. 若权限为“查询”，那么就只能看；若权限为指定查询，需要点击到同名和同课程号	的课程的详情页才可以尽心修改；若权限为全局查询，则都可以修改
3. 修改完成后仍然是需要管理员申请通过
4. 若当前课程是“审核不通过”的状态，教师修改信息时会触发再次提交申请行为；

 

![](https://pic.imgdb.cn/item/65fab8ee9f345e8d03ba71a7.png) 

 

##### **3.3查询课程信息**

\> ***\*描述\****：该功能不需要经过管理员通过，是强类型的权限

\> ***\*最低功能\****：查询已有的课程、查询公开课程库下的所有课程的基本信息(非详细信息)

\> ***\*扩展功能\****：...

\> ***\*特定查询\****：一般只可以查询到教师所负责管理的所有课程信息

![](https://pic.imgdb.cn/item/65fab8a39f345e8d03b91549.png) 

\> ***\*全局查询\****：一般是所有教师所管理的课程（包括自己），一般会对部分信息进行加密（注意：该部分是留给师弟/师妹自行实现，不提供demo；）

 

#### **4.学生功能**

注意：由于上述管理员、教师功能过多，由于只是为了考核，且是为了考察你们的业务逻辑能力，所以这个角色的一些功能可以不需实现（如果时间够的话，可以实现）

这一部分功能在当时候考核提交时会加分（针对你们自己对这个业务的了解）

 

考察：考察你们是否可以根据上述两个角色的功能推断出当前角色具备的一些操作

 

可允许实现的功能：不展示demo

**1.** ***\*查询&修改学生的个人信息功能（头像）\****，可以查询（专业、学号、姓名、身份证、手机号码...）

**2.** ***\*查询期末成绩功能\****

**3.** ***\*选课管理\****（选择选修课）

**4.** ***\*查询课表\****：该项操作是最为难的，需要根据对算法的理解，来生成课表



 

 

## **高级功能**

1. 底层基于Servlet模拟SpringMvc的调度器，减少Servlet的使用，使“普通类也具备请求处理的能力”
2. 整合Jdbc封装一个模板类，将JDBC的繁琐细节封装起来，对外只保留只需要传入sql语句、参数，返回类型的接口，可以借鉴Spring整合JDBC提供的JdbcTemplate
3. 编写缓存池，在Java内存区域下划分出一块缓存区域（定义缓存池类）；可以参考redis数据库的实现，具体借鉴JSR-107规范
4. 数据库对象的使用，除了使用表之外，还可以使用视图、存储对象、触发器来提高持久化查询的效率

 

 

## **考核建议**

1. 需要掌握JavaSE、JavaWeb的语法，考核过程中不建议使用JSP；建议使用原生的那些组件（HTML、CSS、JavaScript）
2. 可以使用部分前端框架、组件优化开发，专注于后端业务的开发
3. 尽可能使用到Servlet、Filter、Listener的生命周期来完成一些业务
4. 在数据库设计方面，请大致浏览一下该考核文档后做出总结
5. 针对于”缓存池的使用“，要考虑到缓存清理问题（可以参考缓存回收策略）
6. 对于可能出现线程安全问题的，可以根据场景选择合适的同步工具类或同步容器或并发容器（Lock、ReentrantLock、CountDownLatch、Semaphore、CyclicBarrier、BlockingQueue...）

7. 在类设计方面，或关系到底层自定义组件，可以从设计模式中寻找灵感
8. 对于一些固定不变的字符串，建议定义为final，优化字符串常量池的执行效率

 

 

## **其他要求**

- 要求分包分类，切勿一个包一个类写到底！！！

- 代码注释务必写好。标明每一个方法的作用、变量的作用等等

- 严禁使用中文拼音或其缩写作为名称。在同一个项目中保持统一的命名规范（建议驼峰式大小写）。命名需要有语义，接近自然语言。尽量少使用临时性命名。可以参照《阿里巴巴Java开发手册》

- 文件编码设置为utf-8。避免在其他人查阅你的代码时无法查看注释



 **杂项**

请为项目附带一份说明文档（推荐使用Markdown进行编写，有图片记得转存pdf），该文档需要写明程序的所有指令的功能，以及指令的使用方式、返回值、程序运行的入口。同时应注明程序运行至哪部分会出现错误及其处理方式（若无，则写暂未解决）。

sql文件，并指定使用的mysql版本  

 

  