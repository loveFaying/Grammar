### 维度调换
```
>>> from einops import rearrange
>>> import torch
>>> a = torch.randn(3,9,9)
>>> rearrange(a, 'h w c -> c h w').shape
torch.Size([9, 3, 9])
```
### 维度拆解
**中间维度看成rxp,给定p的值，系统自动把中间的9拆分成3x3**
```
>>> from einops import rearrange
>>> import torch
>>> a = torch.randn(3,9,9)
>>> rearrange(a, 'c (r p) w -> c r p w', p=3).shape
torch.Size([3, 3, 3, 9])
```
### 复制特征图
```
>>> from einops import repeat
>>> import torch
>>> a = torch.randn(3,9,9)
>>> repeat(a, 'c h w -> b c h w', b=5).shape
torch.Size([5, 3, 9, 9])
```
