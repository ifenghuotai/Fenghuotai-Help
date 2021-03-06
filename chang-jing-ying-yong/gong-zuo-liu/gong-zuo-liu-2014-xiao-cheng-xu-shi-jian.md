# 工作流

### 二、小程序追踪事件触发工作流

位置：登录账号—场景应用—工作流

目的：识别小程序公众号为同一粉丝，根据实际所需情景设置自动化回复与用户秒互动，实现数据打通。

===========================================操作说明======================================================

步骤一：创建小程序追踪配置（具体操作可查看追踪配置说明文档）部分截图

1.新建小程序追踪配置

注意：配置追踪前需要提前接入小程序

![](/assets/xcxlist.png)

2.填写基本信息

![](/assets/xcxjbxx.png)

3.自定义事件属性设置：配置后可以在小程序分析里面看到用户在小程序里面的动作属性信息，例如提交动作、表单填写内容

配置完下载追踪文件嵌入小程序开发中

![](/assets/小程序zdysjsx.png)

步骤二：小程序追踪配置完成后进行工作流的规则设置

1.选择创建好的小程序追踪选择想要触发的事件

注：这里我们拿默认页面展示事件举例，用户也可换其他的事件，视情况而定。

默认事件：小程序打开、小程序退出、小程序页面展示、小程序页面卸载、小程序分享。

自定义事件：自定义的事件名称

![](/assets/xcxmrsj.png)

2.设置流程：下图表示，当粉丝访问了小程序某页面路径，公众号立即回复一条文本消息，并且判断粉丝性别，男女发送不同的消息

一个工作流流程中支持多个事件选择，例如微信事件+小程序事件 

![](/assets/xcxlc.png)







