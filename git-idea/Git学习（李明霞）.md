###### Git学习（李明霞）

我试了将本地分支同步到远程分支的操作。首先想到的是有没有啥快捷方式，然后就找到了这样的一条指令

> git push --set-upstream origin 分支名

但是并没有成功，出现了错误

```
SSL certificate problem:unable to get issuer certificate
```

我查了一下是因为在通过HTTPS访问Git远程仓库时，如果服务器SLL证书未经过第三方机构认证，就会报错。（未知的没有签署过的证书意味着可能存在很大的风险。

solution->将git中的sslverisy关掉

```
git config --global http.sslverify false
```

但是最终也没有解决这个问题，具体原因也还没有找到。