# 将文件a.txt中的前几列输出
```
awk '{print $1,$2,$3 >> "b.txt"}' a.txt
```
