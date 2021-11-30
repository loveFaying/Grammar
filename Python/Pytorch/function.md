### torch.numel(input) → int

**返回输入tensor中元素的总数**

```python
import torch
from icecream import ic

tensor1 = torch.randn(5,5)
tensor2 = torch.randn(3, 5, 5)

ic(tensor1.numel())
# ic| tensor1.numel(): 25
ic(tensor2.numel())
# ic| tensor2.numel(): 75
```

### torch.clamp(input, min=None, max=None, *, out=None) → Tensor

**将input中的所有元素限制在 $[min, max]$ 中**
* 若min是None，则无下界；若max是None，则无上届

```python
import torch 
from icecream import ic  
tensor = torch.randn(5) 

ic(tensor) 
# tensor([ 0.4574,  1.1882,  0.2724, -0.0656, -0.0142])
ic(tensor.clamp(min=-0.5, max=0.5)) 
# tensor([ 0.4574,  0.5000,  0.2724, -0.0656, -0.0142])
ic(tensor.clamp(min=-0.5, max=None)) 
# tensor([ 0.4574,  1.1882,  0.2724, -0.0656, -0.0142])
ic(tensor.clamp(min=None, max=0.5)) 
# tensor([ 0.4574,  0.5000,  0.2724, -0.0656, -0.0142])
ic(tensor.clamp(min=0.5, max=-0.5))
# tensor([ 0.5000, -0.5000,  0.5000,  0.5000,  0.5000])
```

### torch.nn.functional.upsample(input, size=None, scale_factor=None,mode='nearest', align_corners=None)


### torch.nn.KLDivLoss(size_average=None, reduce=None, reduction='mean',log_target=False)

**用于连续分布的距离度量，K-L散度值越小，说明这两个分布越相近**

$$ p(x) $$ : 真实分布   
$$ q(x) $$ : 拟合分布

$$
\begin{align}
D_{DK}(P||Q) &= -\sum_{i}P(i)\ln \frac{Q(i)}{P(i)}  \\
&= \sum_{i}P(i)\ln \frac{P(i)}{Q(i)}   \\
&= \sum_{i=1}^{N}p(x_i) \cdot (\log p(x_i) - \log q(x_i))
\end{align}
$$

