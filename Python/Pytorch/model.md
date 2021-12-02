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

### 冻结模型中某些层，使之不参与训练
- 通过设置参数param的requires_grad属性为False，来冻结该层参数
```
class Net(nn.Module):
    def __init__(self):
        super(Net, self).__init__()
        self.conv1 = nn.Conv2d()
        self.conv2 = nn.Conv2d()
        self.fc1 = nn.Squential(
                                 nn.Linear(),
                                 nn.Linear(),
                                 ReLU(inplace=True),
                                )
 
        for param in self.parameters():
            param.requires_grad = False
        #这样for循环之前的参数都被冻结，其后的正常更新。
        self.classifier = nn.Linear()
```
- 告诉优化器，哪些需要更新，那些不需要
```
optimizer.SGD(filter(lambda p: p.requires_grad, model.parameters()), lr=1e-5)
```
