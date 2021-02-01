# Troubleshooting

We collect the most common troubleshooting of using TensorFlow for your reference:

> Instance troubleshooting is closely related to the Instance provider that is Cloud Platform, refer to [Cloud Platform Documentation](https://support.websoft9.com/docs/faq/tech-instance.html)

#### How can I use the logs?

You can find the keywords **Failed** or **error** from the logs directory: `/data/logs`

#### TensorFlow service can't start?

Insufficient disk space, insufficient memory, and configuration file errors can make service could not be started  

It is recommended to first check through the command.

```shell
# restart TensorFlow service
systemctl status tensorflow
journalctl -u tensorflow

# view disk space
df -lh

# view memory rate
free -lh
```

> Please refer to [official document](https://www.tensorflow.org/install/errors) for more trouble shooting
