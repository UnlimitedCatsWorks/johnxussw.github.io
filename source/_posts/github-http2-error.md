---
title: github-http2-error
date: 2024-03-06 00:09:43
tags:
---

前几天使用git pull命令一直失败，报错如下

```bash
HTTP/2 stream 1 was not closed cleanly before end of the underlying stream
```

稍微查了下，很快在网上找到了答案

全局设置git使用HTTP/1.1就好了

```bash
git config --global http.version HTTP/1.1
```

🤔可是这个报错到底代表了什么呢？
