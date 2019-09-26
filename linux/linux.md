# 查看文件大小
```
du -h 1.txt
```

# 文件从小到大排序
```
ls -lSr
```

# 查看文本行数
```
grep -n '' test1.txt | awk -F : '{print $1}' | tail -n1
```

# 复制前k行至另一个文件
```
head -n 1000 a.txt >b.txt
```

# 从Linux服务器下载文件到本地
```
scp veritas@1.1.1.1:/home/Code/1.txt /home/1.txt 
```