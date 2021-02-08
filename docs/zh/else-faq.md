# FAQ

#### TensorFlow 管理员用户对应的密码是多少？

密码存放在服务器相关文件中：`/credentials/password.txt`

#### TensorFlow 是如何安装的？

是创建 Python 隔离环境后，基于 pip 安装。

#### 是否有可视化的管理工具？

有，内置TensorBoard，访问地址：*http://服务器公网IP:6006/*

#### 是否可以修改TensorFlow的源码路径？

不可以，TensorFlow使用pip安装，服务启动文件设定路径为目前源码路径，修改后服务可能无法启动

#### TensorFlow 实现 GPU 支持需要哪些条件？

需要 NVIDIA® GPU显卡以及驱动程序和工具。详细请参照[TensorFlow GPU 支持软硬件要求](https://www.tensorflow.org/install/gpu)

#### 如何修改上传的文件权限?

```shell
# 拥有者
chown -R nginx.nginx /data/wwwroot/
# 读写执行权限
find /data/wwwroot/ -type d -exec chmod 750 {} \;
find /data/wwwroot/ -type f -exec chmod 640 {} \;
```

#### 部署和安装有什么区别？

部署是将一序列软件按照不同顺序，先后安装并配置到服务器的过程，是一个复杂的系统工程。  
安装是将单一的软件拷贝到服务器之后，启动安装向导完成初始化配置的过程。  
安装相对于部署来说更简单一些。 

#### 云平台是什么意思？

云平台指提供云计算服务的平台厂家，例如：Azure,AWS,阿里云,华为云,腾讯云等

#### 实例，云服务器，虚拟机，ECS，EC2，CVM，VM有什么区别？

没有区别，只是不同厂家所采用的专业术语，实际上都是云服务器