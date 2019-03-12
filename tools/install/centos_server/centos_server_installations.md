# Centos7.2服务器的软件安装

----
## 1 MySQL
### 安装步骤：
  * 下载MySQL源：wget http://dev.mysql.com/get/mysql57-community-release-el7-8.noarch.rpm
  * 安装`MySQL`源：rpm -ivh mysql57-community-release-el7-8.noarch.rpm
  * 安装`mysql-community-server`：yum install mysql-community-server
  * 启动`MySQL`服务：systemctl start mysqld
  * 查看`MySQL`的启动状态：systemctl status mysqld
  * 开机启动：systemctl enable mysqld
  * 配置默认编码为`utf8`：修改/etc/my.cnf配置文件，在[mysqld]下添加编码配置=>[mysqld]\ncharacter_set_server=utf8\ninit_connect='SET NAMES utf8'
  * 查看临时密码：grep 'A temporary password' /var/log/mysqld.log
  * 用临时密码登录`mysql`：mysql -uroot -p
  * 修改`root`密码：`set password for 'root'@'localhost'=password('xxxxxxxx');`**注意：mysql5.7默认安装了密码安全检查插件（validate_password），默认密码检查策略要求密码必须包含：大小写字母、数字和特殊符号，并且长度不能少于8位。否则会提示`ERROR 1819 (HY000): Your password does not satisfy the current policy requirements`错误。**
  * 远程访问root权限：`grant all privileges on *.* to 'root'@'%' identified by 'pwd' with grant option;`
  * 创建MySQL新用户：create user userName identified by 'password';
  * 授权远程访问user用户【将userDb数据库的所有操作权限都授权给了用户user】：grant all privileges on userNameDb.* to userName@'%' identified by 'pwd';\nflush privileges;
  * 修改用户密码：update mysql.user set password = password('pwd') where user = 'userName' and host = '%';\nflush privileges;
  * 删除用户：drop user userName@'%';

## 2 Git
安装命令
```
yum install git
```