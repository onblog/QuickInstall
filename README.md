# QuickInstall

建议使用 Red Hat 系列的 Linux 系统，比如 Centos（已经停止维护）、AlmaLinux（🌟推荐） 和 Rocky Linux。 系统版本至少 8 起步，别安装 7 了，已经过时了

## 一行命令快速安装 Java 环境 ！

jdk-8u181-linux-x64.tar.gz

```shell
cd /usr/local/lib && wget https://repo.huaweicloud.com/java/jdk/8u181-b13/jdk-8u181-linux-x64.tar.gz -O java-temp.tar.gz && tar -zxvf java-temp.tar.gz && rm -rf java-temp.tar.gz && echo "export JAVA_HOME=`pwd`/jdk1.8.0_181" >> /etc/profile && echo 'export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar' >> /etc/profile && echo 'export PATH=${JAVA_HOME}/bin:$PATH' >> /etc/profile && source /etc/profile && java -version
```

amazon-corretto-17-x64-linux-jdk.tar.gz

```shell
cd /usr/local/lib && wget https://corretto.aws/downloads/latest/amazon-corretto-17-x64-linux-jdk.tar.gz -O java-temp.tar.gz && tar -zxvf java-temp.tar.gz && rm -rf java-temp.tar.gz && echo "export JAVA_HOME=`pwd`/amazon-corretto-17.0.18.9.1-linux-x64" >> /etc/profile && echo 'export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar' >> /etc/profile && echo 'export PATH=${JAVA_HOME}/bin:$PATH' >> /etc/profile && source /etc/profile && java -version
```

## 一行命令快速安装 Maven 环境！

apache-maven-3.8.1-bin.tar.gz

```shell
cd /usr/local/lib && wget https://repo.huaweicloud.com/apache/maven/maven-3/3.8.1/binaries/apache-maven-3.8.1-bin.tar.gz -O maven-temp.tar.gz && tar -zxvf maven-temp.tar.gz && rm -rf maven-temp.tar.gz && echo "export MAVEN_HOME=`pwd`/apache-maven-3.8.1" >> /etc/profile && echo 'export PATH=${MAVEN_HOME}/bin:$PATH' >> /etc/profile && source /etc/profile && mvn -v
```

apache-maven-3.9.9-bin.tar.gz

```shell
cd /usr/local/lib && wget https://repo.huaweicloud.com/apache/maven/maven-3/3.9.9/binaries/apache-maven-3.9.9-bin.tar.gz -O maven-temp.tar.gz && tar -zxvf maven-temp.tar.gz && rm -rf maven-temp.tar.gz && echo "export MAVEN_HOME=`pwd`/apache-maven-3.9.9" >> /etc/profile && echo 'export PATH=${MAVEN_HOME}/bin:$PATH' >> /etc/profile && source /etc/profile && mvn -v
```

## 一行命令快速安装 Nginx 环境！

nginx-1.26.1.tar.gz

```shell
mkdir -p /home/work && cd /home/work && wget http://nginx.org/download/nginx-1.26.1.tar.gz && tar -zxvf nginx-1.26.1.tar.gz && rm -rf nginx-1.26.1.tar.gz && yum -y install gcc automake autoconf libtool make && yum -y install gcc gcc-c++ && yum -y install pcre pcre-devel && yum -y install zlib zlib-devel && yum -y install gd-devel && yum -y install openssl openssl-devel && cd nginx-1.26.1 && ./configure --with-http_ssl_module --prefix=/home/work/nginx && make && make install && cd /home/work/nginx/sbin && echo "export NGINX_HOME=/home/work/nginx" >> /etc/profile && echo 'export PATH=${NGINX_HOME}/sbin:$PATH' >> /etc/profile && source /etc/profile && nginx -v && rm -rf /home/work/nginx-1.26.1
```

## 一行命令快速安装 MySQL5.7

OS：Centos 7

```shell
yum localinstall https://dev.mysql.com/get/mysql57-community-release-el7-8.noarch.rpm && rpm --import https://repo.mysql.com/RPM-GPG-KEY-mysql-2022 && yum install -y mysql-community-server && systemctl start mysqld.service && systemctl enable mysqld.service && cat /var/log/mysqld.log|grep 'A temporary password' && mysql -p
```

改密码：

set global validate_password_policy=0; 
set global validate_password_length=1;
set password=password("123456");

[MySQL](https://www.cnblogs.com/kevingrace/p/8340690.html)

OS：Centos 8

```shell
wget http://dev.mysql.com/get/mysql57-community-release-el7-11.noarch.rpm && yum localinstall mysql57-community-release-el7-11.noarch.rpm -y && yum module disable mysql -y && yum install -y dnf-utils && yum-config-manager --enable mysql57-community && yum install -y mysql-community-server --nogpgcheck && systemctl enable mysqld && systemctl start mysqld && grep 'temporary password' /var/log/mysqld.log && mysql -uroot -p
```

[MySQL](https://blog-65j.pages.dev/2024/07/29/Centos8%E6%88%96AlmaLinux8%E5%AE%89%E8%A3%85MySql5.7/)


## 一行命令安装 Redis

```shell
yum install -y redis && sed -i 's/^requirepass.*/requirepass ""/' /etc/redis.conf && sed -i 's/^protected-mode.*/protected-mode no/' /etc/redis.conf && systemctl enable redis && systemctl start redis
```

## 一行命令安装 Node22

```shell
curl -sL https://nodejs.org/dist/v22.0.0/node-v22.0.0-linux-x64.tar.xz | tar -xJf - && sudo mv node-v22.0.0-linux-x64 /opt/nodejs && echo 'export PATH=/opt/nodejs/bin:$PATH' | sudo tee /etc/profile.d/nodejs.sh && source /etc/profile.d/nodejs.sh && node -v
```
