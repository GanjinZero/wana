# 问题描述
ubuntu 16.04安装的docker版本太低了，不支持nvidia-docker，需要升级。升级过程中发现
```
containerd.io : Depends: libseccomp2 (>= 2.4.0) but 2.3.1-2.1ubuntu2~16.04.1 is to be installed
```

# 解决办法
单独安装如下版本containerd.io
```
sudo apt-get install containerd.io=1.2.2-3
```
然后再安装docker-ce和docker-ce-cli
```
sudo apt-get install docker-ce docker-ce-cli
```
