# QuickInstall

> 注意以下都会安装在 /usr/local/lib 目录，只针对 Linux 64 位系统！

## 一行命令快速安装 Java 环境 ！

jdk-8u341-linux-x64.tar.gz

```shell
cd /usr/local/lib && wget https://github.com/onblog/QuickInstallJava/releases/download/Java8/jdk-8u341-linux-x64.tar.gz -O java-temp.tar.gz && tar -zxvf java-temp.tar.gz && rm -rf java-temp.tar.gz && echo "export JAVA_HOME=`pwd`/jdk1.8.0_341" >> /etc/profile && echo 'export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar' >> /etc/profile && echo 'export PATH=${JAVA_HOME}/bin:$PATH' >> /etc/profile && source /etc/profile && java -version
```

## 一行命令快速安装 Maven 环境！

apache-maven-3.8.7-bin.tar.gz

```shell
cd /usr/local/lib && wget https://github.com/onblog/QuickInstall/releases/download/Maven-3.8.8/apache-maven-3.8.8-bin.tar.gz -O maven-temp.tar.gz && tar -zxvf maven-temp.tar.gz && rm -rf maven-temp.tar.gz && echo "export MAVEN_HOME=`pwd`/apache-maven-3.8.8" >> /etc/profile && echo 'export PATH=${MAVEN_HOME}/bin:$PATH' >> /etc/profile && source /etc/profile && mvn -v
```
