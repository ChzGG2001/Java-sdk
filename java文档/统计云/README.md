
##概述

APICloud的 java SDK 基于HttpClient创建的工具类,将统计云Api以面向对象的思想加以封装,支持对象化操作,只需要在你的代码中引入Analytics类,便可以轻松完成统计相关api接口的调用,获取符合条件的数据.



###**构造器**


```构造器
Analytics(appId, appKey,url);
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
- 描述：应用服务器地址，可为空，为空时默认为编译时的服务器地址，例：http://r.apicloud.com

####示例代码

```java
Analytics analytics = new Analytics(appId, appKey,"");
```

###**获取指定应用ID及时间范围内相关应用统计数据信息**

```java
getAppStatisticDataById
```

####参数

startDate

- 类型：字符串
- 默认值：无
- 描述：起始时间("2015-01-01")

endDate

- 类型：字符串
- 默认值：无
- 描述：起始时间("2015-12-31")

####示例代码

```
JSONObject json = analytics.getAppStatisticDataById("2015-01-01", "2015-12-31");
```

###**获取指定应用ID及时间范围内相关应用各版本的统计数据信息**

```java
getVersionsStatisticDataById(String startDate,String endDate);
```

####参数

startDate

- 类型：字符串
- 默认值：无
- 描述：起始时间("2015-01-01")

endDate

- 类型：字符串
- 默认值：无
- 描述：起始时间("2015-12-31")

####示例代码

```
JSONObject json = analytics.getVersionsStatisticDataById("2015-01-01", "2015-12-31");
```

###**获取用户指定应用ID及时间范围内的应用下各版本地理分布统计数据信息**

```java
getGeoStatisticDataById(String startDate,String endDate,String versionCode);
```

####参数

startDate

- 类型：字符串
- 默认值：无
- 描述：起始时间("2015-01-01")

endDate

- 类型：字符串
- 默认值：无
- 描述：起始时间("2015-12-31")

versionCode

- 类型：字符串
- 默认值：无
- 描述：版本号("0.0.1")
####示例代码

```
JSONObject json = analytics.getGeoStatisticDataById("2015-01-01", "2015-12-31","0.0.1");
```

###**获取用户指定应用ID及时间范围内的应用下各版本设备信息分布统计数据信息**

```java
getDeviceStatisticDataById(String startDate,String endDate);
```

####参数

startDate

- 类型：字符串
- 默认值：无
- 描述：起始时间("2015-01-01")

endDate

- 类型：字符串
- 默认值：无
- 描述：起始时间("2015-12-31")

####示例代码

```
JSONObject json = analytics.getDeviceStatisticDataById("2015-01-01", "2015-12-31");
```

###**获取指定应用ID及时间范围内的应用下各版本异常错误统计数据信息**

```java
getExceptionsStatisticDataById(String startDate,String endDate);
```

####参数

startDate

- 类型：字符串
- 默认值：无
- 描述：起始时间("2015-01-01")

endDate

- 类型：字符串
- 默认值：无
- 描述：起始时间("2015-12-31")

####示例代码

```
JSONObject json = analytics.getExceptionsStatisticDataById("2015-01-01", "2015-12-31");
```

###**根据应用异常错误摘要获取异常错误详细信息**

```java
getExceptionsDetailByTitle(String title)
```

####参数

title

- 类型：字符串
- 默认值：无
- 描述：错误摘要信息

####示例代码

```
JSONObject json = analytics.getExceptionsDetailByTitle("title");
```