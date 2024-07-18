# QuickInstall

建议使用 Red Hat 系列的 Linux 系统，比如 Centos（已经停止维护）、AlmaLinux。

## 一行命令快速安装 Java 环境 ！

jdk-8u181-linux-x64.tar.gz

```shell
cd /usr/local/lib && wget https://repo.huaweicloud.com/java/jdk/8u181-b13/jdk-8u181-linux-x64.tar.gz -O java-temp.tar.gz && tar -zxvf java-temp.tar.gz && rm -rf java-temp.tar.gz && echo "export JAVA_HOME=`pwd`/jdk1.8.0_181" >> /etc/profile && echo 'export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar' >> /etc/profile && echo 'export PATH=${JAVA_HOME}/bin:$PATH' >> /etc/profile && source /etc/profile && java -version
```

## 一行命令快速安装 Maven 环境！

apache-maven-3.8.1-bin.tar.gz

```shell
cd /usr/local/lib && wget https://repo.huaweicloud.com/apache/maven/maven-3/3.8.1/binaries/apache-maven-3.8.1-bin.tar.gz -O maven-temp.tar.gz && tar -zxvf maven-temp.tar.gz && rm -rf maven-temp.tar.gz && echo "export MAVEN_HOME=`pwd`/apache-maven-3.8.1" >> /etc/profile && echo 'export PATH=${MAVEN_HOME}/bin:$PATH' >> /etc/profile && source /etc/profile && mvn -v
```

## 一行命令快速安装 Nginx 环境！

nginx-1.26.1.tar.gz

```shell
mkdir -p /home/work && cd /home/work && wget http://nginx.org/download/nginx-1.26.1.tar.gz && tar -zxvf nginx-1.26.1.tar.gz && rm -rf nginx-1.26.1.tar.gz && yum -y install gcc automake autoconf libtool make && yum -y install gcc gcc-c++ && yum -y install pcre pcre-devel && yum -y install zlib zlib-devel && yum -y install gd-devel && yum -y install openssl openssl-devel && cd nginx-1.26.1 && ./configure --with-http_ssl_module --prefix=/home/work/nginx && make && make install && cd /home/work/nginx/sbin && echo "export NGINX_HOME=/home/work/nginx" >> /etc/profile && echo 'export PATH=${NGINX_HOME}/sbin:$PATH' >> /etc/profile && source /etc/profile && nginx -v && rm -rf /home/work/nginx-1.26.1
```

## 一行命令快速安装 MySQL8.0

OS：AlmaLinux 8

```shell
# 默认安装的是MySQL8.0
yum install mysql-server -y

# 无密码登入
mysql -p

# 修改密码
mysql> alter user 'root'@'localhost' identified by '123456';
mysql> flush privileges;

# 设置远程访问，注意防火墙设置
mysql> use mysql
mysql> update user set host='%' where user ='root';
mysql> FLUSH PRIVILEGES;
mysql> GRANT ALL PRIVILEGES ON *.* TO 'root'@'%'WITH GRANT OPTION;
```
[参考](https://blog.csdn.net/h996666/article/details/80921913)

## 一行命令快速安装 MySQL5.7

OS：Centos 7

[MySQL](https://www.cnblogs.com/kevingrace/p/8340690.html)
