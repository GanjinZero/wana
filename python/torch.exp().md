# 问题
- torch.exp(tensor([1,2,3]))
```
RuntimeError: exp_vml_cpu not implemented for 'Long'
```

- torch.exp(tensor([1,2,3]).float())
没有反应

# 环境
Pytorch: 1.2.0
Ubuntu: 16.04

# 解决方案
- torch.exp(t.float())
- https://github.com/pytorch/pytorch/issues/25904
