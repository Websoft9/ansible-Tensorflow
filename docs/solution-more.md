# More

Each of the following solutions has been proven to be effective and we hope to be helpful to you.

## Sample

Refer to [Tensorflow setup wizard](/stack-installation.md#tensorflow-setup-wizard) charter

## TensorBoard Password

This deployment solution use the Nginx htpasswd for TensorBoard authentication, you can modify password by these steps:

1. Edit the Nginx htpasswd file: */etc/nginx/.htpasswd/htpasswd.conf* and modify the password
2. Restart Nginx service
   ```
   sudo systemctl restart nginx
   ```