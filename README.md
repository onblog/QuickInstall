# QuickInstall

> 注意以下都会安装在当前目录，Centos7测试有效！

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

nginx-1.14.0.tar.gz

```shell
wget http://nginx.org/download/nginx-1.14.0.tar.gz && tar -zxvf nginx-1.14.0.tar.gz && rm -rf nginx-1.14.0.tar.gz && cd nginx-1.14.0 && yum -y install gcc automake autoconf libtool make && yum -y install gcc gcc-c++ && yum -y install pcre pcre-devel && yum -y install zlib zlib-devel && yum -y install gd-devel && yum -y install openssl openssl-devel && ./configure --with-http_ssl_module --prefix=`pwd`/nginx && make && make install && cd `pwd`/nginx/sbin && echo "export NGINX_HOME=`pwd`/nginx" >> /etc/profile && echo 'export PATH=${NGINX_HOME}/sbin:$PATH' >> /etc/profile && source /etc/profile && nginx -v
```

## 一行命令快速安装 MySQL5.7

[MySQL](https://www.cnblogs.com/kevingrace/p/8340690.html)
