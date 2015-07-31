
##概述

APICloud的 java SDK 基于HttpClient创建的工具类,将推送云Api以面向对象的思想加以封装,支持对象化操作,只需要在你的代码中引入Push类,便可以轻松完成推送相关api接口的调用,进行相关的操作.



###**构造器**


```java构造器：
Push(appId, appKey, url)
```

####参数

appId：

- 类型：字符串
- 默认值：无
- 描述：应用的id，在APICloud上应用概览里获取，不能为空

appKey：

- 类型：字符串
- 默认值：无
- 描述：应用的安全校验Key，在APICloud上应用概览里获取，不能为空

url：

- 类型：字符串
- 默认值：无
- 描述：应用服务器地址，可为空，为空时默认为编译时的服务器地址，例：https://p.apicloud.com/

####示例代码

Push push = new Push(appId, appKey,"")

<br>
###**推送消息**

```java
pushMessage(String title,String content,int type,Long timer,int platform,String groupName,String userIds)
```

####参数

title:

- 类型：字符串
- 默认值：无
- 描述：消息标题

content:

- 类型：字符串
- 默认值：无
- 描述：消息标题

type:

- 类型：int
- 默认值：无
- 描述：消息类型，1:消息 2:通知

platform:

- 类型：int
- 默认值：无
- 描述： 0 全部平台;  1 ios;  2 android;

groupName:

- 类型：字符串
- 默认值：无
- 描述：推送组名，多个组用英文逗号隔开.默认:全部组。eg.group1,group2 .

userIds:

- 类型：字符串
- 默认值：无
- 描述：推送用户id, 多个用户用英文逗号分隔，eg. user1,user2


####示例代码

```
JSONObject json = push.pushMessage("2", "1", 1, 0, "", "")
```