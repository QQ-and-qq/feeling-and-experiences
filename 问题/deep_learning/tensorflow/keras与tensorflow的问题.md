# keras与tensorflow的问题

版本对应问题

[具体的对应关系]: https://docs.floydhub.com/guides/environments/

运行中出现如下问题

```
ModuleNotFoundError: No module named 'tensorflow.python
```

原因是对应版本的问题，使用pip卸载掉keras，再用conda下载对应版本keras，即可解决问题。（应该是pip和conda下载的文件，被调用是的先后问题（猜测））