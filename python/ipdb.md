# 逐行调试
```
python -m ipdb 1.py
```
- **n** 下一行
- **s** step into
- **b number** 第number行打断点
- **c** 继续
- **r** 运行到当前函数返回
- **w** where

# 打断点
```python
import ipdb
# some code
x = 10
ipdb.set_trace()
y = 20
# other code
```
