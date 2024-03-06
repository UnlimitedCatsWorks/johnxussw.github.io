---
title: npm-package-gitlink-error
date: 2024-03-06 00:10:33
tags:
---

老node项目下载依赖的时候经常会遇到，postscript之类的需要去github上下载的情况

然而git协议下载经常失败

Ex. git://github.com/org/example.git

可以修改git全局配置来强制使用http协议

```bash
git config --global url."https://".insteadOf "git://"
```

git工具在拉取的时候会把git://替换成https://

🤔所以git协议大概是什么样的呢？报错有什么愿意吗？
