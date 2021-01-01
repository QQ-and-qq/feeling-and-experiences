# qt可视化

```
# coding:UTF-8

from PyQt5 import QtCore,QtGui,QtWidgets
import sys
import qtawesome

class MainUi(QtWidgets.QMainWindow):
        def __init__(self):
                super().__init__()
                self.init_ui()

        def init_ui(self):
                # 设置窗口的大小
                self.setFixedSize(960,700)
                # 创建窗口主部件
                self.main_widegt = QtWidgets.QWidget()
                # 创建主部件的窗口布局
                self.main_layout = QtWidgets.QGridLayout()
                # 设置窗口主部件布局为网格布局
                self.main_widegt.setLayout(self.main_layout)

                # 创建左侧部件
                self.left_widget = QtWidgets.QWidget()
                self.left_widget.setObjectName('left_widget')
                # 创建左侧部件的网格布局
                self.left_layout = QtWidgets.QGridLayout()
                # 设置左侧部件布局为网格
                self.left_widget.setLayout(self.left_layout)

                # 创建右侧部件
                self.right_widget = QtWidgets.QWidget()
                self.right_widget.setObjectName('right_widget')
                # 创建右侧部件的网格布局层
                self.right_layout = QtWidgets.QGridLayout()
                # 创建右侧部件布局为网格
                self.right_widget.setLayout(self.right_layout)

                # 左侧部件在第0行第0列，占8行3列
                self.main_layout.addWidget(self.left_widget,0,0,12,2)
                # 右侧部件在第0行第3列，占8行9列
                self.main_layout.addWidget(self.right_widget,0,2,12,10)
                # 设置窗口主部件
                self.setCentralWidget(self.main_widegt)

                # ---------------设置网格内容---------------------
                # 关闭按钮
                self.left_close = QtWidgets.QPushButton("")
                # 空白按钮
                self.left_visit = QtWidgets.QPushButton("")
                # 最小化按钮
                self.left_mini = QtWidgets.QPushButton("")

                # 内容1
                self.left_label_1 = QtWidgets.QPushButton("每日推荐")
                self.left_label_1.setObjectName("left_label")
                # 内容2
                self.left_label_2 = QtWidgets.QPushButton("我的音乐")
                self.left_label_2.setObjectName("left_label")
                # 内容3
                self.left_label_3 = QtWidgets.QPushButton("联系与帮助")
                self.left_label_3.setObjectName("left_label")


                # --------------------------设置字体----------------------
                self.left_layout.addWidget(self.left_mini,0,0,1,1)
                self.left_layout.addWidget(self.left_close,0,1,1,1)
                self.left_layout.addWidget(self.left_visit,0,1,1,1)
                self.left_layout.addWidget(self.left_label_1,1,0,1,3)
                self.left_layout.addWidget(self.left_label_2,5,0,1,3)
def main():
                app = QtWidgets.QApplication(sys.argv)
                gui = MainUi()
                gui.show()
                sys.exit(app.exec_())

if __name__ == '__main__':
            main()



```

