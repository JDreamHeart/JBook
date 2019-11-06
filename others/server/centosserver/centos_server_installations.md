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

## 3 redis
### 3.1 安装依赖库
```
yum install gcc make
```

### 3.2 下载、解压缩、编译安装
```
curl http://download.redis.io/releases/redis-x.x.x.tar.gz -o redis-x.x.x.tar.gz
tar zxvf redis-x.x.x.tar.gz
cd redis-x.x.x
make
cd src
make install
```

### 3.3 设置为自启动，开机自启
```
# 运行安装服务工具，根据提示设置
# 直接自动帮你安装服务，还可以自定义安装参数。全部默认的话，就会自动产生上述的环境文件和服务文件，且已经打开了服务。 默认的服务名为redis_6379
./utils/install-server.sh
# 启动
systemctl start redis_6379
# 开机启动
systemctl enable redis_6379
# 查看状态
systemctl status redis_6379
```

## 4 httpd
安装命令
```
yum install httpd
```
启动服务
```
systemctl start httpd.service
```
停止服务
```
systemctl stop httpd.service
```
重启服务
```
systemctl restart httpd.service
```
设置apache开机启动
```
systemctl enable httpd.service
```

## 5 安装python3
下载安装命令
```
wget https://www.python.org/ftp/python/版本号/文件名.tgz
tar zxvf 文件名.tgz
cd 文件名
./configure
make
make install
```
