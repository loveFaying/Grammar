### 查看数据和模型在GPU还是CPU上
```Python
model = get_AF_DUNet_crfasrnn()
print(next(model.parameters()).device)  # 模型
inputs = torch.rand(3, 512, 512).unsqueeze(0).cuda()
print(inputs.device)
```
