# 初始化安装

在云服务器上部署 TensorFlow 预装包之后，请参考下面的步骤快速入门。

## 准备

1. 在云控制台获取您的 **服务器公网IP地址** 
2. 在云控制台安全组中，检查 **Inbound（入）规则** 下的 **TCP:6006** 端口是否开启
3. 若想用域名访问 TensorFlow，请先到 **域名控制台** 完成一个域名解析

## TensorFlow 验证向导

1. 使用 SSH 登录服务器后，查看 TensorFlow 服务状态
   ```
   sudo systemctl status tensorflow
   ```
2. 使用本地电脑的浏览器访问网址：*http://域名:6006* 或 *http://服务器公网IP:6006*, 进入登陆页面

3. 输入账号密码（[不知道账号密码？](/zh/stack-accounts.md#rocketmq)），成功登录到 TensorBoard
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/tensorflow/tensorflow-board-websoft9.png)

> 需要了解更多 TensorFlow 的使用，请参考官方文档：[TensorFlow Documentation](https://www.tensorflow.org/learn)

## TensorFlow 入门向导

下面通过运行一个 TensorFlow 范例，演示它的计算结果：

1. 使用 SSH 连接到服务器，运行下面的命令
   ```
   cd /data/apps/tensorflow
   source /data/apps/tensorflow/bin/activate
   python3 tensorflow_test.py
   ```
2. 登录到 TensorBoard，此时页面已经有运行的内容
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/tensorflow/tensorflow-simpletest-websoft9.png)

## 常见问题

#### 浏览器打开IP地址，无法访问 TensorFlow（白屏没有结果）？

您的服务器对应的安全组6006端口没有开启（入规则），导致浏览器无法访问到服务器的任何内容

#### 使用 TensorFlow 的时候为什么需要先 `source /data/apps/tensorflow/bin/activate` ？

本部署方案中 TensorFlow 使用的 Python 隔离环境安装