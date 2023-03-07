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
取消全局代理：
git config --global --unset http.proxy
 
git config --global --unset https.proxy
```

