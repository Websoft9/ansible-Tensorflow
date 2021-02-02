# Initial Installation

If you have completed the TensorFlow deployment on Cloud Platform, the following steps is for you to start use it quikly

## Preparation

1. Get the **Internet IP** on your Cloud Platform
2. Check you **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the TCP:6006 is allowed
3. Make a domain resolution on your DNS Console if you want to use domain for TensorFlow

## TensorFlow install verification

### Verification by shell command

After logging in to the server with SSH, run the following commands to check whether TensorFlow is installed correctly.
```
sudo systemctl status tensorflow
```

### Verified by visual tools

1. Use local Chrome or Firefox to access the URL *http://DNS:6006* or *http://Server's Server's Internet IP:6006*. Enter the login page.
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/tensorflow/tensorflow-loginonly-websoft9.png)

2. Log in RocketMQ-Console-Ng console. ([Don't have password?](/stack-accounts.md#tensorflow)), the page prompts that there are no active events 
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/rocketmq/rocketmq-console-websoft9.png)

 > More useful TensorFlow guide, please refer to [TensorFlow Documentation](https://www.tensorflow.org/install)

## TensorFlow Setup wizard

After the installation, tensorboard prompts that there are no active events. Here is a simple example to use tensorflow. The steps are as follows:

1. Running tensorflow application example
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
2. Back to TensorBoard page, the graph changes:
 ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/tensorflow/tensorflow-simpletest-websoft9.png)


## Q&A

#### I can't visit the start page of TensorFlow?

Your TCP:6006 of Security Group Rules is not allowed so there no response from Chrome or Firefox