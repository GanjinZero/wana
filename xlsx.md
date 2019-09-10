# 问题
R安装xlsx时有问题，需要先配置Java，再配置rJava才行

# 解决方案(未完)
```
sudo apt-get install default-jre
sudo apt-get install default-jdk
sudo
R CMD javareconf
```
这时再安装rJava提示：checking whether JNI programs can be compiled... configure: error: Cannot compile a simple JNI program.
https://github.com/s-u/rJava/issues/200
