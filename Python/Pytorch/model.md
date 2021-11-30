### 输出模型的参数量

```python
import torchvision.models as models

num_params = 0
resnet50 = models.resnet50(pretrained=False)
# resnet50.load_state_dict(torch.load("resnet50-19c8e357.pth"))
for param in resnet50.parameters():
    num_params += param.numel()
print("The number of parameters : %.3f M" % (num_params/1e6))
# The number of parameters : 25.557 M
```
