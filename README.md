## 前端技术栈

Vue + icework (通过API连接后端)

## 项目运行

```
1、icework
2、mongodb/redis/mysql( 开启状态)

```
### 主要页面

- 管理员页面：区别于网站页面，负责赛程安排
- 添加比赛：裁判员获得比赛ID输入，使用API，后端将比赛存储在数据库中
- 安排赛程：安排队伍名称，安排比赛赛程

### 裁判员后台比赛录入流程图

```flow
st=>start: 记录比赛ID添加进后台系统
op=>operation: 后台根据比赛ID获取比赛数据，存储进MongoDb数据库
op2=>operation: 后台逻辑更新队伍数据
cond=>condition: 存储成功 Yes or No?
e=>end: 同步前台
st->op->op2->cond
cond(yes)->e
cond(no)->op
```
### NOSQL数据：
- 经API获取后台处理形成数据存储

| 名称  | 键  | 值|
| :------------ |:---------------:| 
| 比赛数据     | matchdata | 比赛队伍,选手表现数据，建筑物数据，一血时间等 |
| 选手数据     | playerdata | 积分，平均比赛KDA，比赛总金额经验等  |
| 队伍数据 | teamdata | 5名选手ID+N替补ID |
       
----
