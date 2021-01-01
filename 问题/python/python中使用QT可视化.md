# python中使用QT可视化

## 一、配置运行环境

### 1.cmd激活虚拟环境

```
active tensorflow-gpu
```

如果没有环境，可以新建一个新的环境

```
pip create -n py36 python=3.6 
```

### 2.先安装qt依赖包（pyqt是QT在python上的一个最支持的库，pyqt5-tools是用于设计qt界面使用，用于生成.ui文件，pyuic5是用于将.ui文件转化为.py文件）

```
pip install pyqt5 -i https://pypi.tuna.tsinghua.edu.cn/simple

pip install pyqt5-tools -i https://pypi.tuna.tsinghua.edu.cn/simple

pip install pyuic5 -i https://pypi.tuna.tsinghua.edu.cn/simple
```

### 3.在pycharm中配置依赖包

#### 3.1现在pycharm的设置中选择新建的环境，如图所示：

![image-20201124101033181](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201124101033181.png)

3.2依然在pycharm设置中点击tool按钮，选择external tools添加如下文件：

![image-20201124101336551](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201124101336551.png)

点击添加会出现以下界面：

![image-20201124101413908](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201124101413908.png)

首先先添加pyqt5-tool依赖包，添加内容如下：

##### name：QtDesinger（名字可以随意）

##### program：D:\ProgramData\Anaconda3\envs\tensorflow-gpu\Scripts\pyqt5designer.exe（该地址改为自己的，一般在安装的环境下的）

![image-20201124102331846](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201124102331846.png)

如果找不到该文件，可以在以下地方找到：

![image-20201124102618773](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201124102618773.png)

##### working directory：$FileDir$（该处跟我的一样即可，表示当前项目的下）

![image-20201124102804883](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201124102804883.png)

其次添加转化依赖包pyuic5：

跟上一个依赖包同样的步骤

##### name：pyuic5（名字随意）

##### program：D:\ProgramData\Anaconda3\envs\tensorflow-gpu\Scripts\pyuic5.exe（换成自己的地址）

![image-20201124103206677](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201124103206677.png)

##### argument：$FileName$-o$FileNameWithoutExtension$.py（此处跟我填成一样的，大致意思是转化时需要提供参数，下面会说解释）

##### working directory：$FileDir$（该处跟我的一样即可，表示当前项目的下）

![image-20201124103420882](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201124103420882.png)

此处我还多添加了一个依赖包，但是发现可以不用，如下所示：

步骤都一样，只有**argument：\$FileNameWithoutExtension$.py**不一样

![image-20201124103517922](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201124103517922.png)

全部添加好后如下所示：

![image-20201124103632040](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201124103632040.png)

### 4.打开配置好的文件

![image-20201124104037779](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201124104037779.png)

##### 4.1点击后出现：

![image-20201124104115836](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201124104115836.png)

**此处如果遇到错误，那可能时argument参数不对（检查下就行）**

##### 4.2点击新建即可

![image-20201124104251819](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201124104251819.png)

![image-20201124104335066](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201124104335066.png)

##### 4.3拖动左侧文件进行设计

![image-20201124105250682](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201124105250682.png)

##### 4.4保存文件，如果选择默认，就是保存在当前项目下，如图：

![image-20201124110638004](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201124110638004.png)

##### 4.5然后打开terminal窗口，运行pyuic5 -o test_demo.py test_demo.ui

![image-20201124111723108](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201124111723108.png)

##### 4.6即可生成.py文件

![image-20201124111907321](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201124111907321.png)

### 5.运行.py文件，实现可视化展示

如果直接运行文件，不会出现任何的结果，需要添加如下代码：

```
if __name__ == "__main__":
    import sys
    app = QtWidgets.QApplication(sys.argv)
    Form = QtWidgets.QMainWindow()
    ui = Ui_Dialog() #这个是类名，名字根据自定义的情况变化
    ui.setupUi(Form)
    Form.show()
    sys.exit(app.exec_())
```

![image-20201124112220887](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201124112220887.png)

修改以后，直接点击运行即可显示：

![image-20201124112402121](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201124112402121.png)