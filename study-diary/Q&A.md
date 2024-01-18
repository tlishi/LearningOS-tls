#### Q1：git push提交时遇到fatal: unable to access 'https...

这种情况是因为虽然开着代理，但`git push`可能还是没走代理，需要在git上配置

可以在git上敲：

```
git config --global --get http.proxy
git config --global --get https.proxy
```

查看两个协议的代理模式



然后通过

```
git config --global http.proxy 'socks5://127.0.0.1:1080' 
git config --global https.proxy 'socks5://127.0.0.1:1080'
```

设置git代理，1080是默认端口号，有可能大家的不一样，自行查看自己代理客户端，选择正确的设置。



比如我用的v2ray，我的代理端口是10808。

更多详细信息参考这两链接：

[为什么开了代理，git push 还是很慢或报错](https://blog.csdn.net/qq_42951560/article/details/124332605)

[git设置、查看、取消代理](https://www.cnblogs.com/yongy1030/p/11699086.html)