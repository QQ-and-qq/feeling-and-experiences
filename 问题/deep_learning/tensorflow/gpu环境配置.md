# gpu环境配置

### 一、查看电脑N卡信息

![image-20201222144720057](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201222144720057.png)

### 二、下载对应版本的cuda

[下载]: https://developer.nvidia.com/cuda-toolkit-archive

![image-20201222145747391](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201222145747391.png)

如图所示，选择：CUDA Tookit 9.0——>Windows——>x86_64——>7（代表Windows 7）——>exe(local) ——>Download(1.4GB)

本次下载的程序为：**cuda_9.0.176_windows.exe**

**注意：**选择合适的系统win10，win8还是win7；推荐选择exe（local）版，network版在安装过程中下载东西，可能导致安装过程很长长长长......

**安装：**默认“下一步”即可完成安装

查看是否成功，打开cmd，输入

```
nvcc --version
```

显示如下，即安装成功了

![image-20201222173706464](C:/Users/YYQ/AppData/Roaming/Typora/typora-user-images/image-20201222173706464.png)

### 三、下载支持版本的cudnn

版本查看

[查看版本]: https://blog.csdn.net/qq_29678299/article/details/88227990

![img](https://img-blog.csdnimg.cn/20190306123848922.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI5Njc4Mjk5,size_16,color_FFFFFF,t_70)

[下载]: https://developer.nvidia.com/rdp/cudnn-archive

![image-20201222145847500](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201222145847500.png)

选择cuDNN v7.5.0 for CUDA 9.0进行下载，本次下载后的文件为：**cudnn-9.0-windows7-x64-v7.5.0.56.zip**

解压该文件，并将bin、include和lib三个文件夹复制到CUDA安装目录下。

**注意**：提示文件夹重复时选择“合并”即可。

### 四、安装tensorflow-gpu

打开cmd进行安装

```
pip install tensorflow-gpu==1.9 -i https://pypi.tuna.tsinghua.edu.cn/simple
```

### 五、打开pycharm测试gpu

配置自己的运行环境

![image-20201222174020090](C:/Users/YYQ/AppData/Roaming/Typora/typora-user-images/image-20201222174020090.png)

输入测试代码

```
import tensorflow as tf
hello = tf.constant('Hello, TensorFlow!')
sess = tf.Session()
print(sess.run(hello))
```

