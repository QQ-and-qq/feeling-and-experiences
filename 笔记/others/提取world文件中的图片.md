# 提取world文件中的图片

1.将world文档的后缀**.doc或.docx**重命名改为**.rar或.zip**即可，如图：

![image-20201119144258163](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201119144258163.png)![image-20201119144315477](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201119144315477.png)

2.将压缩包解压，可得到如下文件夹：

![image-20201119144410181](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201119144410181.png)

3.点击打开其中的word，图片全部放在media文件夹中，如图：

![image-20201119144511352](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201119144511352.png)

4.使用如下代码将全部图片转换为**.jpg格式**的图片。

代码如下：

```
# _*_ coding:UTF-8 _*_

# 导入os模块
import os
# 创建文件夹
if not os.path.exists('jpg图片'):
    os.makedirs('jpg图片')

path = r'./jpg图片'
# 列出media文件夹下的图片
files = os.listdir(r'./media')

for item in files:
    # 拼接出media文件夹下所有图片路径
    files_1 = './media'+'/'+item
    # 读取图片数据
    with open(files_1,'rb') as f:
        con = f.read()
    # 重新写入以.jpg格式并保存到jog图片文件夹
    files_name = path+'/'+item.split('.')[0]+'.jpg'
    with open(files_name,'wb') as f:
        f.write(con)
```

文件夹如下所示：

![image-20201119144657061](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201119144657061.png)

即在**jpg图片**文件夹中得到**.jpg后缀**的图片，如图：

![image-20201119144808552](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201119144808552.png)

