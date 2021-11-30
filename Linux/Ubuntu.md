### 查看cuda版本号
```bash
nvcc -V
```

### 批量压缩
分卷压缩dataset_512 , 使得每个不超过 2000M
```bash
tar -czf - dataset_512 | split -b 2000m -d - mass.tar.gz
```
将分卷压缩合并成一个
```bash
cat mass.tar.gz* > mass.tar.gz
```
解压mass.tar.gz 到当前目录
```bash
tar -xzf mass.tar.gz
```
将各个分卷压缩包解压到当前目录
```bash
cat mass.tar.gz* | tar -xzf -
```
