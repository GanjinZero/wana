# 将文件a.txt中的前几列输出
```
awk '{print $1,$2,$3 >> "b.txt"}' a.txt
```

# 句子乱序
```
awk 'BEGIN{srand()}{b[rand()NR]=$0}END{for(x in b)print b[x]}' tmp.txt
```
