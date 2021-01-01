# python代码打包exe

## 1.测试自己的代码是否正常运行

### 1.1打开cmd，将运行地址cd到项目地址下

![image-20201207151729979](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201207151729979.png)

### 1.2在该地址下运行需要生成exe的.py文件

## 2.没有问题之后在该项目路径下，输入(-F 如果没有这个生成的不只是单一的exe)

```
pyinstaller -F 自己的.PY
```

![image-20201207152520510](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201207152520510.png)

## 3.一直等到以下代码出现，即可

![image-20201207152814300](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201207152814300.png)

## 4.在该项目地址下生成两个文件夹，分别是dist和build文件夹，其中exe在dist文件中

![image-20201207153600413](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201207153600413.png)

![image-20201207153644876](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201207153644876.png)

**缺点：容易被人将代码反编译！！！！！**

# 第二种方法：可以先使用Cython将python转化为.c文件，再通过c语言编译器，将c语言转化为.exe文件。

## 1.先安装Cython

```
pip install Cython
```

## 2.python到c的转化

使用命令行进入到目标python文件xxx.py的目录下，执行命令：

```
cython xxx.py --embed
```

## 3.转化时注意事项

文件中可能存在a.b.py的情况，可以更改为a_b.py

![image-20201207155744076](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201207155744076.png)

出现这个即为转化成功，警告不知道什么意思，不影响。

## 4.将c文件编译成为exe文件

### 4.1gcc编译的失败

```
gcc xxx.py -o xxx.exe
```

![image-20201207160932347](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201207160932347.png)

[参考]: https://blog.csdn.net/weixin_38098596/article/details/106023956?utm_source=app

