## 卸载JDK

1.高级设置- >JAVA_HOME->找到jdk所在路径，将整个JDK文件夹删除

2.清除环境  JAVA_HOME删除   path中Java相关环境删除

3.查看 java --version



## 安装JDK

1. 搜搜jdk8
2. 同意协议
3. 下载安装版本
4. 记住安装路径
5. 配置环境变量
6.  
   1. 我的电脑 右键 属性 高级系统设置
   2. 环境变量--系统变量---JAVA_HOME
   3. 配置path  %JAVA_HOME%bin
   4. 配置path  %JAVA_HOME%jre
7. 测试JDK是否成功
   1. 打开cmd
   2. java -version