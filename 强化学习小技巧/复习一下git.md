## 复习一下git

```
git add *
git commit -m "注释"
git push origin main
```

git push连接失败的解决方案

```
git config --global http.sslVerify "false"
```

push不上别慌，取消梯子的全局代理先

```
git config --global http.proxy http://127.0.0.1:1080
git config --global https.proxy http://127.0.0.1:1080
```

