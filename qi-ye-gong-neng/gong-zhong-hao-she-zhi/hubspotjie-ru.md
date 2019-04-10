# 接入hubspot设置

位置：登录账号—企业功能—公众号设置—接入hubspot

目的：借助Hubspot，打通微信粉丝与联系人之间的同步数据，您可以拿到：

* 微信公众号内粉丝通过手机号、邮箱、点击链接等自定义方式自动在Hubspot平台创建新的联系人

* Hubspot联系人属性信息\(姓名、邮箱、手机号等\)以及用户行为可以自动同步至烽火台客户画像

* Hubspot联系人中可获取微信粉丝的基本属性\(OPENID、昵称、地理位置等\)以及粉丝行为轨迹

以下是如何入门：

注意：接入hubspot 首先需要有hubspot开发者账号和应用登录账号

#### 步骤一：创建hubspot app

##### 注：若没有hubspot相应页面权限请联系您账号管理员调整权限

1.登录开发者账号，选择“Apps”菜单，创建application并保存

#### ![](/assets/createhubspot.png)

#### 步骤二：登录烽火台账号，接入hubspot

1.找到企业功能-公众号设置-接入hubspot，点击接入，进入配置填写页面

配置填写页面如下：接入名称可以自定义，其余6个参数如何获取详见下文

![](/assets/createhubspotjieru.png)

![](/assets/jieruhubspot.png)

2.返回hubspot创建页面，在application列表中选择新创建的application，点击Edit获取信息，并勾选三项授权

复制APPID 、Client ID、Client secret填写在烽火台相应的配置文本框中

![](/assets/hqapp.png)

三项授权如下：

![](/assets/gxsq.png)

3.返回创建application列表页面，点击Get HAPIkey获取HAPIKEY 、User ID

复制HAPIKEY 、User ID填写在烽火台相应的配置文本框中

![](/assets/haip.png)

#### 步骤三：登陆hubspot应用账号，获取相应配置信息填入输入框中

1.登录hubspot找到右上角的个人资料，点击integrations，获取API KEY

#### ![](/assets/qh.png)

2.点击左侧API key，复制值填写在烽火台相应的配置文本框中

![](/assets/apikeys.png)

#### 步骤四：填写完毕接入成功

1.保存后进入授权页面

![](/assets/savelist.png)

2.点击Grant access 进入接入跳转页面

![](/assets/shouquan.png)![](/assets/jieruyanzheng.png)

接入完毕进入烽火台的hubspot列表，可进行删除和编辑操作

* 编辑：配置信息填写错误时可进行修改

* 删除：删除接入账号，一旦删除将不再同步数据

#### ![](/assets/hubspotlb.png)



