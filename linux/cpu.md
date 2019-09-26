# 查看CPU型号
```
cat /proc/cpuinfo | grep name | cut -f2 -d: | uniq -c 
```

# 查看物理CPU的个数
```
cat /proc/cpuinfo |grep "physical id"|sort |uniq|wc -l
```

# 查看逻辑CPU的个数
```
cat /proc/cpuinfo |grep "processor"|wc -l
```

# 查看CPU是几核
```
cat /proc/cpuinfo |grep "cores"|uniq 
```