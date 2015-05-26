本项目起源于[show-me-the-code][1]的第25题，并根据这个需求，完成了该语音控制电脑的程序。最终代码在[Github * longstreetcc * Voice-Ctrl-Computer][2]上，使用的语言是Python。实际测试可用，如需添加功能，可以阅读代码。


---

##安装环境

该软件需要导入很多工具包，除了以下两个包，其他的包都在python 2.76里面自带了。因此这两个包需要从外部安装。

    import pyaudio 
    import requests

requests 可以通过pip安装。`pip install requests`，pyaudio需要下载安装包。下载地址[http://people.csail.mit.edu/hubert/pyaudio/][3]。安装好对应版本后，就可以执行本程序了。

---

##设计思路

该项目的基本思路是
- 录音
- 语音命令翻译成文字命令
- 识别文字命令
- 根据命令执行程序



###录音

录音功能可以采用pyaudio软件提供方的例子，或[http://sebug.net/paper/books/scipydoc/wave_pyaudio.html][4]的教程



###语音识别

本项目使用的是[百度语音识别][5]REST API接口加以实现的。百度语音识别不仅提供了Android、iOS的SDK，还提供了该Rest API方式进行语音识别。通过python的requests包进行上报语音，返回语音识别的结果。


###执行命令

针对返回的语音结果，返回汉字，对汉字进行解析，通过命令行的方式，打开应用程序。针对不同的系统，用户可以修改该部分来执行所在操作系统的命令。

---

##用法

加入shebang `#! /usr/bin/env python` 更改执行方式，`chmod a+x app.py`，在命令行通过`./app.py`来执行。





[1]:https://github.com/longstreetcc/show-me-the-code
[2]:https://github.com/longstreetcc/Voice-Ctrl-Computer
[3]:http://people.csail.mit.edu/hubert/pyaudio/
[4]:http://sebug.net/paper/books/scipydoc/wave_pyaudio.html
[5]:http://yuyin.baidu.com/

