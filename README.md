# 京东自动签到(TG bot消息)

### 功能：
1. 获取签到最新代码
2. 替换参数值
3. 签到并发送通知

详情参考文章:[京东定时签到-GitHub 实现](https://ruicky.me/2020/06/05/jd-sign/) 

### 在原项目基础上的改动

- 微信模版消息替换为telegram机器人消息
- 每12小时执行一次

### telegram bot消息接入

1. ##### 创建自己的电报机器人

   首先，通过以下链接连接到 @BotFather : https://telegram.me/BotFather 。当在电报中打开与 BotFather 的聊天窗口时，按下**Start**按钮。

   ![image-20210223171615168](https://tva1.sinaimg.cn/large/008eGmZEly1gnxl61eyhqj30ik0e6wh6.jpg)

   按 **/newbot** 命令，依次并输入您的机器人的name和username, 然后会获得机器人的token

   ![image-20210223171854355](https://tva1.sinaimg.cn/large/008eGmZEly1gnxl8r3pnij30va04yq3z.jpg)

   

2. ##### 给自己的bot发送消息获取chatID

   发送消息之后访问https://api.telegram.org/bot<YourBOTToken>/getUpdates获取消息

   ![image-20210223172402751](https://tva1.sinaimg.cn/large/008eGmZEly1gnxle3yezoj30pl0jgabv.jpg)

   chatId就是了

3. ##### 配置 github secrets

   机器人toke对应secret name为TG_BOT_TOKEN

   chatId对应secret name为CHAT_ID![image-20210223172841765](https://tva1.sinaimg.cn/large/008eGmZEly1gnxlu2kg3rj30oo062gm3.jpg)



当这些都配置好了, github workflow执行的时候就会收到机器人的消息了
