有时使用一段时间系统，经常会发生apt-get异常，如果报如下错误

```
Encountered a section with no Package: header
...
```

则这样做（我也不知道为什么，估计是和缓存有关）

```
sudo rm /var/lib/apt/lists/* -vf
sudo apt-get update
```

来源http://blog.csdn.net/hs794502825/article/details/7835902