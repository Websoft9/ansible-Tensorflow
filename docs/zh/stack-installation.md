# 初始化安装

在云服务器上部署 TensorFlow 预装包之后，请参考下面的步骤快速入门。

## 准备

1. 在云控制台获取您的 **服务器公网IP地址** 
2. 在云控制台安全组中，检查 **Inbound（入）规则** 下的 **TCP:6006** 端口是否开启
3. 若想用域名访问 TensorFlow，请先到 **域名控制台** 完成一个域名解析

## 验证安装是否成功

### 通过shell命令验证

使用SSH登录到服务器后，运行如下几个命令，检查TensorFlow是否正确安装
```
sudo systemctl status tensorflow
```

### 通过可视化工具验证
1. 使用本地电脑的 Chrome 或 Firefox 浏览器访问网址：*http://域名:6006* 或 *http://服务器公网IP:6006*, 进入登陆页面
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/tensorflow/tensorflow-loginonly-websoft9.png)

2. 输入账号密码（[不知道账号密码？](/zh/stack-accounts.md#rocketmq)），成功登录到 TensorBoard，页面提示没有活动事件
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/tensorflow/tensorflow-board-websoft9.png)

> 需要了解更多 TensorFlow 的使用，请参考官方文档：[TensorFlow Documentation](https://www.tensorflow.org/install)

## TensorFlow 入门向导

安装完成后，TensorBoard提示没有活动事件，下面将通过简单的例子来使用TensorFlow，步骤如下：
在发送/接收消息之前，我们需要告诉客户端名称服务器的位置。RocketMQ提供了多种方法来实现这一目标。为简单起见，我们使用环境变量`NAMESRV_ADDR`，实现流程如下：
```
 > export NAMESRV_ADDR=localhost:9876
 > sh bin/tools.sh org.apache.rocketmq.example.quickstart.Producer
 SendResult [sendStatus=SEND_OK, msgId= ...

 > sh bin/tools.sh org.apache.rocketmq.example.quickstart.Consumer
 ConsumeMessageThread_%d Receive New Messages: [MessageExt...
```
 >完成后发现TensorBoard 界面产生变化：
 ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/rocketmq/rocketmq-send-websoft9.png)



## 常见问题

#### 浏览器打开IP地址，无法访问 TensorFlow（白屏没有结果）？

您的服务器对应的安全组6006端口没有开启（入规则），导致浏览器无法访问到服务器的任何内容