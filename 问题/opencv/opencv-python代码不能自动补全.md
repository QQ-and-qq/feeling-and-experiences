# opencv-python代码不能自动补全

### 问题原因：

opencv所有的代码都在**cv2.data**文件下面而不是cv2文件下面

### 解决办法：

导入时使用

```
import cv2.cv2 as cv
```

可以**自动代码补齐**，但是出现新的问题：

module'cv2.cv2'has no attribute'cv2'

此时我查看了以下opencv-python的版本，卸载了之后发现还存在另外一个版本，此时可以正常的运行代码也可以正常的显示代码，导入的包如下：

```
import cv2 as cv
```

