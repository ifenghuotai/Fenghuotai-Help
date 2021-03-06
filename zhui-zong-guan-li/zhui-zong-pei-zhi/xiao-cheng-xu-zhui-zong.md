# 二、小程序追踪配置

位置：登录账号-追踪管理-追踪配置-选择小程序追踪

目的：掌握用户行为并分析报表

注意：**公众号和小程序需绑定在同一个开放平台上，小程序需在微信后台关联公众号**

追踪流程如下：

### 一：接入小程序

##### 步骤一：企业功能—公众号设置—接入小程序—接入

![](/assets/jieruxiaochengxu.png)

##### 步骤二：如图所示填上正确的信息—确定后即可

![](/assets/creatxiaochengxu.png)

### 二：小程序配置

位置：登录账号-追踪管理-追踪配置-选择小程序追踪

注意：一个小程序只允许创建一个追踪，多个小程序可创建多个追踪

![](/assets/xiaochengxulist.png)

##### 1.选择追踪类型—小程序追踪

##### 2.新建追踪

a.填入追踪描述、选择小程序，点击下一步设置属性

![](/assets/zc.png)

b.设置事件属性（自定义属性、默认属性）—保存

默认属性：平台默认追踪的一些属性事件，可以在小程序事件分析中查出数据

![](/assets/shuixing.png)

自定义属性：若默认属性不满足客户需求，可以追踪自定义属性

填写的属性名需与小程序内追踪代码保持一致

![](/assets/zdyxcxsx.png)

##### 3.查看创建后的追踪文件并进行其他操作\(请勿恶意操作导致查询不出数据概不负责\)

![](/assets/listlist.png)

a.编辑：手误写错时方便修改内容

b.下载追踪文件：创建追踪后需手动下载文件导入到代码工程中即可。\(如何嵌入和使用追踪文件详见第三项：小程序嵌入sdk配置\)

c.删除：删除该小程序追踪，数据也将清零

注：追踪完成后，可进入仪表盘—小程序分析查看报表、事件追踪中查看事件数据

### 三：小程序嵌入sdk配置

#### 1.设置域名

登录微信公众平台\(mp.weixin.qq.com\)，在**开发**—**开发设置**—**服务器域名**找到request合法域名，点击修改，将  tracking.ifenghuotai.cn添加到request合法域名中，只有管理员有此权限

![](/assets/mpxcxszym.png)

#### 2.配置sdk

1.下载sdk并将下载文件解压，将解压后的文件**fht-tracking-miniapp-config.js**和**fht-tracking-miniapp-sdk.js**放置在小程序任意目录下\(两文件位置上没有限制，但必须是平级目录\)

![](/assets/zzwjjy.png)

2.使用微信开发者工具打开小程序根目录下的**app.js**文件，复制下段代码到**app.js**文件的第一行并保存。

### **const sdk = require\('./fhtTracking-miniapp-sdk-src'\);**

下图示例中sdk文件是放在小程序根目录下，所以不需要加其他目录名称，若在其他目录下，请加上目录名。

![](/assets/fzdm.png)

以上是单纯追踪默认事件和属性的配置，只能查看报表；若需要追踪自定义事件和属性，且通过工作流给触达小程序的公众号粉丝下发消息、打标签等操作，详见下方高级功能说明

### 高级功能

#### UnionID 机制说明

如果开发者拥有多个移动应用、网站应用、和公众帐号（包括小程序），可通过 UnionID 来区分用户的唯一性，因为只要是同一个微信开放平台帐号下的移动应用、网站应用和公众帐号（包括小程序），用户的 UnionID 是唯一的。换句话说，同一用户，对同一个微信开放平台下的不同应用，UnionID是相同的。

上报用户unionid烽火台自动获取

##### 上报用户unionid：

```js
wx.login({
  success(res) {
    if (res.code) {
      //发起网络请求
      sdk.userRegister(res.code)
    } else {
      console.log('登录失败！' + res.errMsg)
    }
  }
})
```

##### 更新用户信息

```js
wx.getUserInfo({
  success: function (res) {
    sdk.addUser(res.userInfo)
  }
})
```

##### 

自定义事件是烽火台平台提供的自助分析功能，用户在小程序上的行为我们定义为事件。例如：手机号授权登录、账号密码登录、注册...可以帮助您更好的分析用户的关键行为，做到针对性运营。自定义事件可以在高级分析中的小程序追踪里查看以及工作流中选择事件条件配置相关流程。

注：event键值对不可更改，value的键值对可自行命名（烽火台前端显示页面用key显示事件名）

##### 自定义事件：

```js
sdk.send({
  event: "custom_event",
  //具体的事件的值，如订单号，金额等
  value: {
    orderNumber: "189731794"
  }
})
```



