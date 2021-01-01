# pycharm活动模板

## 1.编辑好需要生成模板的代码，如下所示：

```
# 1.导入需要的包
import sys
from PyQt5 import QtCore, QtGui, QtWidgets
# 2.生成一个应用程序窗口
app = QtWidgets.QApplication(sys.argv)
# 3.在窗口内添加控件
Form = QtWidgets.QMainWindow()
Form.setWindowTitle("")
# ---------------------添加控件----------


# 4.展示控件
Form.show()
# 5.使窗口一直显示并接受窗口信息，打印消息
sys.exit(app.exec_())
```

## 2.打开pycharm的设置，搜索live templates，打开python并点击右侧的＋进行添加

![image-20201126105753580](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201126105753580.png)

3.点击+选择live templates，按照下面步骤进行添加，如果需要快速定位到模板某个位置，可以在该位置添加如下代码：$TITLE$或$BODY$

![image-20201126110440546](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201126110440546.png)

4.在页面直接输入自己设置的活动模板快捷键即可，如下：

![image-20201126110714113](C:/Users/YYQ/AppData/Roaming/Typora/typora-user-images/image-20201126110714113.png)

![image-20201126110727709](C:/Users/YYQ/AppData/Roaming/Typora/typora-user-images/image-20201126110727709.png)