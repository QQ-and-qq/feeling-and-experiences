# 代码上传

## 1.注册GitHub账号

[注册网页]: https://github.com/

## 2.创建仓库

注册完成后登录，在登录界面选择右上角的“+”，选择new repository创建一个新的仓库

![image-20201202145151723](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201202145151723.png)

点击后进入仓库设置，填写仓库名称、仓库说明、仓库权限以及说明文档等。

![image-20201202150417517](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201202150417517.png)

生成后的仓库如下：

![image-20201202150525356](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201202150525356.png)

## 3.安装git客户端

[下载地址]: https://gitforwindows.org/

github是个服务端，我们需要自己电脑上使用git客户端，直接下载安装即可，一路点NEXT就行，任何文件夹点击右键可以看到Git GUI here 和Git Bash here就说明安装成功了。

## 4.配置Git

可以在电脑任意位置存放本地仓库，例如我的是D:\git下，这个根据个人爱好

#### 1.鼠标右击选择Git Bash here，此时出现一个命令框，输入git init，敲回车，会发现在git文件夹下多出一个.git文件，此时表示git创建成功，如图所示：

![image-20201202155538103](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201202155538103.png)

![image-20201202155410150](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201202155410150.png)

#### 2.在本地创建ssh key

输入ssh-keygen -t -C"自己的邮箱"，直接点击回车即可（**该邮箱是在GitHub上注册的邮箱**）

![image-20201202160818119](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201202160818119.png)

其中的Enter file in which to save the key ：**这个会自动生成，直接点回车即可，如果输入了内容会在当前文件夹下生成ssh key（最好自动生成，不确定会不会有别的影响），例如：**

![image-20201202161101784](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201202161101784.png)

Enter passphrase (empty for no passphrase):**表示输入登录的密码，直接点回车就是无密码（不知道为什么输入不了）**

Enter same passphrase again:**再次确认密码，如果没有直接回车即可**

Your identification has been saved in xxxxxx **表示生成ssh key的地址**

#### 3.进入ssh key的地址查看

![image-20201202161645913](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201202161645913.png)

直接打开id_rsa.pub文件，复制里面的内容，打开查看是否是以ssh-rsa开头的，如果是就说明没有错。

#### 4.回到GitHub网站，进入主页点击头像下面的setting（如果打开的是仓库会没有该选项，返回主页就行）

![image-20201202162231453](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201202162231453.png)

点击ssh and gpg keys，选择new ssh key

![image-20201202162704477](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201202162704477.png)

将复制的内容粘贴进行即可

![image-20201202162615596](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201202162615596.png)

出现以下界面就是表示成功了。

![image-20201202162921162](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201202162921162.png)

#### 5.验证是否成功

回到git bash界面去，输入以下代码

```
ssh -T git@github.com
```

出现以下界面说明连接成功

![image-20201202163359671](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201202163359671.png)

注意：中间会出现询问，是因为并不是在当前文件夹下连接的，只是一种安全验证，直接输入yes即可

连接成功后会多出来一个known_hosts文件

![image-20201202163716521](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201202163716521.png)

#### 6.此时就是将本地仓库上传到GitHub上去，先设置GitHub上的name和email，分别输入以下命令

```
git config --global user.name"自己的名字“
git config --global user.email"自己的邮箱"
```

![image-20201202164242173](C:\Users\YYQ\AppData\Roaming\Typora\typora-user-images\image-20201202164242173.png)

7.然后将项目上传到github，进入要上传的仓库，右键进入git bash，添加远程地址

```
git remote add origin git@github.com:you_name/you_repo
```

对应GitHub上的：

![image-20201202170910089](C:/Users/YYQ/AppData/Roaming/Typora/typora-user-images/image-20201202170910089.png)

结果如下：

![image-20201202170723977](C:/Users/YYQ/AppData/Roaming/Typora/typora-user-images/image-20201202170723977.png)

# 5.上传提交

1.将项目上传到待提交区域

```
git add .
```

![image-20201202171211705](C:/Users/YYQ/AppData/Roaming/Typora/typora-user-images/image-20201202171211705.png)

2.提交所有代码

```
git commit -m "上传代码的注释"
```

![image-20201202171522632](C:/Users/YYQ/AppData/Roaming/Typora/typora-user-images/image-20201202171522632.png)

3.从本地仓库推送到远程服务器

```
git push origin master
```

![image-20201202171806072](C:/Users/YYQ/AppData/Roaming/Typora/typora-user-images/image-20201202171806072.png)



此时查看GitHub就可以看到项目

![image-20201202173348218](C:/Users/YYQ/AppData/Roaming/Typora/typora-user-images/image-20201202173348218.png)



