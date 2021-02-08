# Parameters

The TensorFlow deployment package contains a sequence software (referred to as "components") required for TensorFlow to run. The important information such as the component name, installation directory path, configuration file path, port, version, etc. are listed below.

## Path

### TensorFlow

TensorFlow installation directory:  */data/apps/tensorflow*  
TensorFlow logs directory:  */data/logs/tensorflow*  
TensorFlow configuration file:  */data/apps/tensorflow/conf*  

### Nginx

Nginx vhost configuration file: */etc/nginx/conf.d/default.conf*    
Nginx main configuration file: */etc/nginx/nginx.conf*   
Nginx logs file: */var/log/nginx*  
Nginx rewrite rules directory: */etc/nginx/conf.d/rewrite*  
Nginx htpasswd file: */etc/nginx/.htpasswd/htpasswd.conf*

## Ports

Open or close ports by **[Security Group Setting](https://support.websoft9.com/docs/faq/tech-instance.html)** of your Cloud Server to decide whether the port can be accessed from Internet.  

You can run the cmd `netstat -tunlp` to check all related ports.  

The following are the ports you may use:

| Name | Number | Use |  Necessity |
| --- | --- | --- | --- |
| HTTP | 6006 | HTTP requests for TensorBoard| Required |


## Version

You can see the version on product pages at Marketplace. However, after being deployed to your server, the components will be updated automatically, resulting in a certain change in the version number. Therefore, run the command on the server to view the exact version number. 

```shell
# Check all components version
sudo cat /data/logs/install_version.txt

# Linux Version
lsb_release -a

# Nginx  Version
nginx -V

# Nginx  Version
nginx -V

# python version
python3 -v

# TensorFlow version
/tensorflow/bin/tensorboard --version_tb
```
