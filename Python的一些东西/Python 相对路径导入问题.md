我碰到了一个问题，关于Python相对路径倒入的问题
我的文件结构如下

/flask_app
    app.py
    models.py
    
当我想在 app.py 中调用 models.py 中的一个类时
1. from models import *
    这样子的话，命令行下 python3 app.py 可以正常使用，pycharm 也可以运行
    但是 pycharm IDE 无法识别上下文，也就是说IDE认为我没有成功导入
2. from .models import *
    这样子 IDE 识别了，但是IDE 和命令行都不能运行，报错
3. from flask_app.models import *
    这样子，IDE 可以识别，并且都可以运行调试
    
感觉这个问题是 IDE 的问题