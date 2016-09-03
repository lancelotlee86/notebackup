一般来说直接
    pip install some_models.whl
就可以

但是在PyCharm中，我试了这样子安装的话，PyCharm不能正确识别这个模块，没法import，代码运行也是错误的

所以在尝试上面那个方法后可以再试一下，在IDE下方的 Python Console 中
    import pip
    pip.main(['install', 'some_models.whl'])
然后我的IDE就神奇的开始indexing，然后模块的识别也正常了。
在IDE中安装的模块列表中也可以看到新安装的模块了
