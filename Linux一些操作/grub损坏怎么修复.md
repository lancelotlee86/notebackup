#### 怎么进入正常的grub

有时会碰到开机时直接gurb报错

```
  error: file '/boot/grub/i386-pc/normal.mod' not found.
  Entering rescue mode...
  grub rescue>
```

1. 输入ls，查看硬盘分区信息，得到
```
  (hd0)  (hd0,msdos14) (hd0,msdos13) (hd0,msdos12)....
```

2. 挨个试
```
  ls (hd0,msdos1)/boot/grub
```
有时因为linux默认的文件安装目录不同，尝试以下
```
  ls (hd0,msdos1)/grub
```

3. 碰到某个磁盘分区没有报`error filesystem`
```
  set root=(hd0,msdos13)
  set prefix=(hd0,msdos13)grub
  insmod normal
  normal
```
就可以进入grub了

[参考](http://jingyan.baidu.com/article/c85b7a640cd7d6003bac95f8.html "")

#### 进入linux后怎么修复
1. 挂载分区
```
sudo mount /dev/sda7 /mnt   # 前面那个/dev/sda7指代的是/boot的盘符
sudo /dev/sda6 /mnt/boot    # 前面那个/dev/sda6指代的是/的盘符
```

2. 重装grub
```
sudo grub-install --boot-directory=/mnt/boot/ /dev/sda    # 这个前面的路径是你挂载/boot分区的路径,后面的路径是你的硬盘
```

3. 更新一下grub
```
sudo update-grub
```

至此结束

[参考](http://blog.sina.com.cn/s/blog_5d5b98ff0101fkwx.html)
