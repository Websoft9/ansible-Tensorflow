# Initial Installation

If you have completed the TensorFlow deployment on Cloud Platform, the following steps is for you to start use it quickly

## Preparation

1. Get the **Internet IP** on your Cloud Platform
2. Check you **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the TCP:6006 is allowed
3. Make a domain resolution on your DNS Console if you want to use domain for TensorFlow

## TensorFlow Verify Wizard

1. Use SSH to connect Server, run the following command to check the status of TensorFlow
   ```
   sudo systemctl status tensorflow
   ```

2. Refer to [Web-based GUI](/solution-gui.md) to access TensorBoard


 > More useful TensorFlow guide, please refer to [TensorFlow Documentation](https://www.tensorflow.org/learn)

## TensorFlow Setup wizard

Now, we run a TensorFlow sample for quick start:

1. Use SSH to connect Server, running the sample script by the following commands
   ```
   cd /data/apps/tensorflow
   source /data/apps/tensorflow/bin/activate
   python tensorflow_test.py
   ```

2. Login to TensorBoard, you can see the graph changed
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/tensorflow/tensorflow-simpletest-websoft9.png)


## Q&A

#### I can't visit the start page of TensorFlow?
Your TCP:6006 of Security Group Rules is not allowed so there no response from Chrome or Firefox

#### Why should I run `source /data/apps/tensorflow/bin/activate`?

This TensorFlow used Python environment for deployment