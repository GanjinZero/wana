# 升级依赖有问题
ubuntu 16.04安装的docker版本太低了，不支持nvidia-docker，需要升级。升级过程中发现
```
containerd.io : Depends: libseccomp2 (>= 2.4.0) but 2.3.1-2.1ubuntu2~16.04.1 is to be installed
```

## 解决办法
单独安装如下版本containerd.io
```
sudo apt-get install containerd.io=1.2.2-3
```
然后再安装docker-ce和docker-ce-cli
```
sudo apt-get install docker-ce docker-ce-cli
```

# 无法用gpu启动
参见这个[issue](https://github.com/NVIDIA/nvidia-docker/issues/838)
```
sudo docker run -it --rm --gpus all tensorflow/tensorflow:latest-gpu python
```

# 继续报错
```
docker: Error response from daemon: OCI runtime create failed: container_linux.go:344: starting container process caused "process_linux.go:424: container init caused \"process_linux.go:407: running prestart hook 0 caused \\\"error running hook: exit status 1, stdout: , stderr: nvidia-container-cli: requirement error: unsatisfied condition: cuda>=10.1, please update your driver to a newer version, or use an earlier cuda container\\\\n\\\"\"": unknown.
```
