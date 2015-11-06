#### 安装Qt
直接官网上的在线安装, 没费事儿.

#### 安装sip
> sudo python3 configure.py
> sudo make
> sudo make install

我碰到了一个问题,提示缺少 Python.h 头文件, 解决方法是
> sudo apt-get install python-dev

#### 安装pyqt
> sudo python3 configure.py --qmake /opt/Qt/......# the path of qmake
> sudo make
> sudo make install

我的默认的 /usr/bin 中的 qmake 貌似是 qt3 的, 所以我在后面指定了 qmake 的路径
进入 python3 后, 尝试 import PyQt5, 发现不成功, 最后才发现放有 PyQt5 模块的 site-packages 目录不在 $PYTHONPATH 中
> export PYTHONPATH=/usr/lib/python3.4/site-packages:$PYTHONPATH

我的 PyQt5 的包还不完整, 只能导入 QtCore 等几个模块, QtGui 和 QtWidgets 都无法导入, 折腾了一下午!! 终于在 stackoverflow 上找到了原因!!! 是因为我的 OpenGL 不完整导致的!!! 
> sudo apt-get install libgl1-mesa-dev libgl1-mesa-glx

无语了..不过真的谢谢 stackoverflow ,比百度知道靠谱多了, 最无奈的是百度知道上有人在 Qt 的问题下面回复 "QT不是语音聊天软件么.."