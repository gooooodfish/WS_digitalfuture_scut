# Fixes

### 下载环境文件

https://c-t.work/s/fca20305057c49

在这个网址上下载环境包，解压，注意不要有双层目录

### 删除原DF2019环境

管理员模式进入anaconda

输入

```
conda remove -n DF2019 --all
```

### 复制新环境

打开anaconda的安装位置

![1568210814079](Fixes.assets/1568210814079.png)

进入envs文件夹，把解压出来的DF2019文件夹复制到这里

![1568210881186](Fixes.assets/1568210881186.png)

### 安装fofin—UI

以管理员进入anaconda Prompt

```
conda activate DF2019
```

打开compas_fofin—UI解压的位置

```
cd C:\ ...\compas_fofin-UI
```

输入以下两条命令

```
python -m compas_rhino.uninstall_plugin FOFIN{7ea0207d-965a-4982-abc7-f60810ae2626}
```

```
python -m compas_rhino.install_plugin FOFIN{7ea0207d-965a-4982-abc7-f60810ae2626}
```

### 在anaconda里打开proxy服务器

输入

python

再输入

```
>>>from compas.rpc import Proxy
```

```
>>>p=Proxy()
```

![1568211720681](Fixes.assets/1568211720681.png)

此时不要关闭anaconda，直接打开rhino6

### Rhino6里fofin找形

用管理员模式打开rhino6

输入命令fofin_init

![1568216038786](Fixes.assets/1568216038786.png)

在rhino里画一个网格平面

![1568216153991](Fixes.assets/1568216153991.png)

fofin_from

mesh

再选中该曲面

![1568216200137](Fixes.assets/1568216200137.png)

fofin_attributes     vertices    选中四个顶点

![1568216275114](Fixes.assets/1568216275114.png)

将is_anchor改成True

![1568216297128](Fixes.assets/1568216297128.png)

输入命令fofin_run

![1568216338179](Fixes.assets/1568216338179.png)

即得到找形结果
