# 更多...

下面每一个方案，都经过实践证明行之有效，希望能够对你有帮助

## 应用示例

参考本文档 [tensorflow-入门向导](/zh/stack-installation.md#tensorflow-入门向导) 相关章节。

## 密码管理

本部署方案通过 Nginx 验证访问控制 TensorBoard 的访问，通过如下两个步骤修改密码：

1. 编辑 Nginx 验证访问控制文件： */etc/nginx/.htpasswd/htpasswd.conf* 中的密码
2. 重启 Nginx 服务后生效
   ```
   sudo systemctl restart nginx
   ```