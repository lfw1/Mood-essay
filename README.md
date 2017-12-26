# Mood-essay
首先到官网Download JDK下载jdk压缩文件，我这里下载的是 jdk-7u79-linux-x64.tar.gz
创建jdk的安装目录（当然，您可以创建自己喜欢的目录名） /usr/lib/jvm，然后将jdk文件拷贝到刚刚创建的安装目录/usr/lib/jvm 
然后运行sudo tar -zvxf jdk-7u79-linux-x64.tar.gz  解压jdk文件。
配置jdk的环境变量  vi /etc/profile ,然后在文件的最后添加一下内容（添加内容所涉及到的目录需根据自己的实际情况修改）
JAVA_HOME=/usr/lib/jvm/jdk1.7.0_79
PATH=$JAVA_HOME/bin:$PATH
CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
export JAVA_HOME
export PATH
export CLASSPATH
让配置文件生效，执行 source /etc/profile 。
验证是否安装成功，在终端输入java -version，如果出现一下类似内容，那就说明安装成功了。
java version "1.7.0_79"
Java(TM) SE Runtime Environment (build 1.7.0_79-b15)
Java HotSpot(TM) 64-Bit Server VM (build 24.79-b02, mixed mode)

网友的建议：

不建议把jdk环境变量写入profile文件中，这成了整个系统的jdk变量。

 建议写在tomcat的startup.sh和shutdown.sh文件中，这样每个tomcat都可以根据自己的需要使用.
