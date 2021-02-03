# 初始化安装

在云服务器上部署 TensorFlow 预装包之后，请参考下面的步骤快速入门。

## 准备

1. 在云控制台获取您的 **服务器公网IP地址** 
2. 在云控制台安全组中，检查 **Inbound（入）规则** 下的 **TCP:6006** 端口是否开启
3. 若想用域名访问 TensorFlow，请先到 **域名控制台** 完成一个域名解析

## TensorFlow 安装向导

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
1. 运行TensorFlow应用例
```
cd /data/apps/tensorflow
source /data/apps/tensorflow/bin/activate
python tensorflow_test.py

(tensorflow) root@iZj6cgvr9r6lehhsl9up9fZ:/data/apps/tensorflow# python tensorflow_test.py
2021-02-01 15:50:07.644082: W tensorflow/stream_executor/platform/default/dso_loader.cc:60] Could not load dynamic library 'libcudart.so.11.0'; dlerror: libcudart.so.11.0: cannot open shared object file: No such file or directory
2021-02-01 15:50:07.644123: I tensorflow/stream_executor/cuda/cudart_stub.cc:29] Ignore above cudart dlerror if you do not have a GPU set up on your machine.
Downloading data from https://storage.googleapis.com/tensorflow/tf-keras-datasets/mnist.npz
11493376/11490434 [==============================] - 0s 0us/step
2021-02-01 15:50:10.347277: I tensorflow/compiler/jit/xla_cpu_device.cc:41] Not creating XLA devices, tf_xla_enable_xla_devices not set
2021-02-01 15:50:10.351127: W tensorflow/stream_executor/platform/default/dso_loader.cc:60] Could not load dynamic library 'libcuda.so.1'; dlerror: libcuda.so.1: cannot open shared object file: No such file or directory
2021-02-01 15:50:10.351159: W tensorflow/stream_executor/cuda/cuda_driver.cc:326] failed call to cuInit: UNKNOWN ERROR (303)
2021-02-01 15:50:10.351193: I tensorflow/stream_executor/cuda/cuda_diagnostics.cc:156] kernel driver does not appear to be running on this host (iZj6cgvr9r6lehhsl9up9fZ): /proc/driver/nvidia/version does not exist
2021-02-01 15:50:10.351518: I tensorflow/core/platform/cpu_feature_guard.cc:142] This TensorFlow binary is optimized with oneAPI Deep Neural Network Library (oneDNN) to use the following CPU instructions in performance-critical operations:  AVX2 AVX512F FMA
To enable them in other operations, rebuild TensorFlow with the appropriate compiler flags.
2021-02-01 15:50:10.351727: I tensorflow/compiler/jit/xla_gpu_device.cc:99] Not creating XLA devices, tf_xla_enable_xla_devices not set
2021-02-01 15:50:10.445424: I tensorflow/core/profiler/lib/profiler_session.cc:136] Profiler session initializing.
2021-02-01 15:50:10.445465: I tensorflow/core/profiler/lib/profiler_session.cc:155] Profiler session started.
2021-02-01 15:50:10.446864: I tensorflow/core/profiler/lib/profiler_session.cc:172] Profiler session tear down.
2021-02-01 15:50:10.807437: I tensorflow/compiler/mlir/mlir_graph_optimization_pass.cc:116] None of the MLIR optimization passes are enabled (registered 2)
2021-02-01 15:50:10.824709: I tensorflow/core/platform/profile_utils/cpu_utils.cc:112] CPU Frequency: 2500010000 Hz
Epoch 1/5
   1/1875 [..............................] - ETA: 14:03 - loss: 2.2938 - accuracy: 0.18752021-02-01 15:50:11.339254: I tensorflow/core/profiler/lib/profiler_session.cc:136] Profiler session initializing.
2021-02-01 15:50:11.339304: I tensorflow/core/profiler/lib/profiler_session.cc:155] Profiler session started.
2021-02-01 15:50:11.345715: I tensorflow/core/profiler/lib/profiler_session.cc:71] Profiler session collecting data.
2021-02-01 15:50:11.354333: I tensorflow/core/profiler/lib/profiler_session.cc:172] Profiler session tear down.
2021-02-01 15:50:11.366301: I tensorflow/core/profiler/rpc/client/save_profile.cc:137] Creating directory: /data/logs/tensorflow20210201-155010/train/plugins/profile/2021_02_01_15_50_11
2021-02-01 15:50:11.367143: I tensorflow/core/profiler/rpc/client/save_profile.cc:143] Dumped gzipped tool data for trace.json.gz to /data/logs/tensorflow20210201-155010/train/plugins/profile/2021_02_01_15_50_11/iZj6cgvr9r6lehhsl9up9fZ.trace.json.gz
2021-02-01 15:50:11.379630: I tensorflow/core/profiler/rpc/client/save_profile.cc:137] Creating directory: /data/logs/tensorflow20210201-155010/train/plugins/profile/2021_02_01_15_50_11
2021-02-01 15:50:11.379732: I tensorflow/core/profiler/rpc/client/save_profile.cc:143] Dumped gzipped tool data for memory_profile.json.gz to /data/logs/tensorflow20210201-155010/train/plugins/profile/2021_02_01_15_50_11/iZj6cgvr9r6lehhsl9up9fZ.memory_profile.json.gz
2021-02-01 15:50:11.379912: I tensorflow/core/profiler/rpc/client/capture_profile.cc:251] Creating directory: /data/logs/tensorflow20210201-155010/train/plugins/profile/2021_02_01_15_50_11Dumped tool data for xplane.pb to /data/logs/tensorflow20210201-155010/train/plugins/profile/2021_02_01_15_50_11/iZj6cgvr9r6lehhsl9up9fZ.xplane.pb
Dumped tool data for overview_page.pb to /data/logs/tensorflow20210201-155010/train/plugins/profile/2021_02_01_15_50_11/iZj6cgvr9r6lehhsl9up9fZ.overview_page.pb
Dumped tool data for input_pipeline.pb to /data/logs/tensorflow20210201-155010/train/plugins/profile/2021_02_01_15_50_11/iZj6cgvr9r6lehhsl9up9fZ.input_pipeline.pb
Dumped tool data for tensorflow_stats.pb to /data/logs/tensorflow20210201-155010/train/plugins/profile/2021_02_01_15_50_11/iZj6cgvr9r6lehhsl9up9fZ.tensorflow_stats.pb
Dumped tool data for kernel_stats.pb to /data/logs/tensorflow20210201-155010/train/plugins/profile/2021_02_01_15_50_11/iZj6cgvr9r6lehhsl9up9fZ.kernel_stats.pb
1875/1875 [==============================] - 6s 3ms/step - loss: 0.3591 - accuracy: 0.8947 - val_loss: 0.1066 - val_accuracy: 0.9691
Epoch 2/5
1875/1875 [==============================] - 5s 3ms/step - loss: 0.0993 - accuracy: 0.9700 - val_loss: 0.0773 - val_accuracy: 0.9761
Epoch 3/5
1875/1875 [==============================] - 5s 3ms/step - loss: 0.0663 - accuracy: 0.9799 - val_loss: 0.0698 - val_accuracy: 0.9776
Epoch 4/5
1875/1875 [==============================] - 5s 3ms/step - loss: 0.0498 - accuracy: 0.9838 - val_loss: 0.0730 - val_accuracy: 0.9775
Epoch 5/5
1875/1875 [==============================] - 5s 3ms/step - loss: 0.0398 - accuracy: 0.9869 - val_loss: 0.0646 - val_accuracy: 0.9801
```
2. 返回TensorBoard 页面，图形发生变化：
 ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/tensorflow/tensorflow-sampletest-websoft9.png)

## 常见问题

#### 浏览器打开IP地址，无法访问 TensorFlow（白屏没有结果）？

您的服务器对应的安全组6006端口没有开启（入规则），导致浏览器无法访问到服务器的任何内容