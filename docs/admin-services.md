# Start or Stop the Services

These commands you must know when you using the TensorFlow of Websoft9

### TensorFlow

```shell
sudo systemctl start tensorflow-server
sudo systemctl stop tensorflow-server
sudo systemctl restart tensorflow-server
sudo systemctl status tensorflow-server

# you can use this debug mode if TensorFlow service can't run
tensorflow-server console
```

### MySQL

```shell
sudo systemctl start mysql
sudo systemctl stop mysql
sudo systemctl restart mysql
sudo systemctl status mysql
```

### Redis

```shell
systemctl start redis
systemctl stop redis
systemctl restart redis
systemctl status redis
```
