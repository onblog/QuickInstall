# QuickInstallJava

一行命令快速安装 Java 环境 ！

> 注意 jdk 文件夹将会被放置在 /usr/local/lib

# Linux

## jdk-8u341-linux-x64.tar.gz

```shell
cd /usr/local/lib && wget https://github.com/onblogs/QuickInstallJava/releases/download/Java8/jdk-8u341-linux-x64.tar.gz -O java-temp.tar.gz && tar -zxvf java-temp.tar.gz && rm -rf java-temp.tar.gz && echo "export JAVA_HOME=`pwd`/jdk1.8.0_341" >> /etc/profile && echo 'export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar' >> /etc/profile && echo 'export PATH=${JAVA_HOME}/bin:$PATH' >> /etc/profile && source /etc/profile && java -version
```

## jdk-8u341-linux-aarch64.tar.gz

```shell
cd /usr/local/lib && wget https://github.com/onblogs/QuickInstallJava/releases/download/Java8/jdk-8u341-linux-aarch64.tar.gz -O java-temp.tar.gz && tar -zxvf java-temp.tar.gz && rm -rf java-temp.tar.gz && echo "export JAVA_HOME=`pwd`/jdk1.8.0_341" >> /etc/profile && echo 'export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar' >> /etc/profile && echo 'export PATH=${JAVA_HOME}/bin:$PATH' >> /etc/profile && source /etc/profile && java -version
```

## jdk-8u341-linux-i586.tar.gz

```shell
cd /usr/local/lib && wget https://github.com/onblogs/QuickInstallJava/releases/download/Java8/jdk-8u341-linux-i586.tar.gz -O java-temp.tar.gz && tar -zxvf java-temp.tar.gz && rm -rf java-temp.tar.gz && echo "export JAVA_HOME=`pwd`/jdk1.8.0_341" >> /etc/profile && echo 'export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar' >> /etc/profile && echo 'export PATH=${JAVA_HOME}/bin:$PATH' >> /etc/profile && source /etc/profile && java -version
```
