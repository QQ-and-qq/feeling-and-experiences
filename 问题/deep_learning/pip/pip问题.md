1.遇到pip更新问题

```
WARNING: You are using pip version 20.2.2; however, version 20.2.4 is available.
You should consider upgrading via the 'd:\programdata\anaconda3\envs\tensorflow-gpu\python.exe -m pip install --upgrade pip' command.
```

**解决方法：**

- [x] 1.pip install --upgrade pip

出现新的问题：

```
ERROR: Could not install packages due to an EnvironmentError: [WinError 5] 拒绝访问。: 'd:\\programdata\\anaconda3\\envs\\tensorflow-gpu\\scripts\\pip.exe'
Consider using the `--user` option or check the permissions.
```

再次使用：

```
python -m pip install --upgrade pip
```

又出现：

 No module named pip.__main__; 'pip' is a package and cannot be directly executed

再次使用：

python -m ensurepip

出现新问题

```
ModuleNotFoundError: No module named 'pip._internal.cli'
```

`未解决问题`

最后解决方法

[https://www.it610.com/article/1290965411088637952.htm]: 解决方法

