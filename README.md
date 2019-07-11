# PyQt5 教程阅读须知
 
“PyQt5 教程” 系列若不做明显提示，默认翻译自 zetcode。
有需要翻译精度的朋友可以自行阅读英文文档。

## PyQt5 介绍
这是一份 PyQt5 的教程。教程的目的是让你开始学会使用 PyQt5 工具包。这个教程的内容在 Linux 上创建并测试。

## PyQt5 相关
PyQt5 是一套来自 Digia 的 Qt5 应用框架和 Python 的粘合剂。支持 Python2.x 和 Python3.x 版本。本教程使用 Pyhton 3。Qt 库是最强大的 GUI 支持库的一种。PyQt5 的官方主页是 www.riverbankcomputing.co.uk/news。是 Riverbank Computing 开发了 PyQt5。

PyQt5 以一套 Python 模块的形式来实现功能。**它包含了超过 620 个类，600 个方法和函数**。它是一个多平台的工具套件，它可以运行在所有的主流操作系统中，包含 Unix，Windows 和 Mac OS。PyQt5 采用双重许可模式。开发者可以在 GPL 和社区授权之间选择。

PyQt5 的类被划分在几个模块中，下面列出了这些模块：

- QtCore 模块包含了非 GUI 的功能设计。这个模块被用来实现时间，文件和目录，不同数据类型，流，URL，mime 类型，线程和进程。
- QtGui 模块包含的类用于窗口化的系统结构，事件处理，2D 绘图，基本图形，字体和文本。
- QtWidgets 模块包含的类提供了一套 UI 元素来创建经典桌面风格用户界面。
- QtMultimedia 模块包含的类用于处理多媒体内容和链接摄像头和无线电功能的 API。QtBluetooth 模块包含的类用于扫描蓝牙设备，并且和他们建立连接互动。
- QtNetwork 模块包含的类用于网络编程，这些类使 TCP/IP 和 UDP 客户端 / 服务端编程更加容易和轻便。
- QtPositioning 模块包含的类用于多种可获得资源的位置限定，包含卫星定位，Wi-Fi，或一个文本文件。
- Enginio 模块用于解决客户端访问 Qt 云服务托管。 
- QtWebSockets 模块包含的类用于解决 WebSocket 通信协议。 
- QtWebKit 包含的关于浏览器的类用于解决基于 WebKit2 的支持库。 
- QtWebKitWidgets 模块包含的关于 WebKit1 的类基本解决浏览器使用基于 QtWidgets 应用问题。 
- QtXml 模块包含的类用于解析 XML 文件。这个模块提供 SAX 和 DOM API 解决方法。 
- QtSvg 模块提供类用于显示 SVG 文件内容。Scalable Vector Graphics (SVG) 是一种语言，用 XML 来描述二维图形和图形应用程序。 
- QtSql模块提供类驱动数据库工作。 
- QtTest 模块包含了方法提供PyQt5应用的单元测试。

PyQt4 和 PyQt5 的不同之处
The PyQt5 is not backward compatible with PyQt4; there are several significant changes in PyQt5. However, it is not very difficult to adjust older code to the new library. The differences are, among others, the following:

PyQt5 不向后兼容 PyQt4；这是一些在 PyQt5 中的重要改变。然而，将旧代码迁移到新的版本中并不是非常困难。不同点如下：

Python 模块已经被改写. 一些模块被舍弃 (QtScript), 部分的模块被分割成子模块 (QtGui, QtWebKit).
新的模块被引进, 包含 QtBluetooth, QtPositioning, 和 Enginio.
PyQt5 只支持最新风格的信号和槽的写法. SIGNAL() 和 SLOT() 的调用将不会被长时间支持.
PyQt5 不支持任何在 Qt 5.0 版本中弃用或取消的 API.

## 用PyQt5写的第一个程序
在这篇PyQt5教程中，我们可以学习一些PyQt5的基础应用。

 
 
## 简单的例子
这是一个显示一个小窗口的简单例子。我们可以做许多这样的窗口。我们可以调整它的**窗口尺寸，最大化或最小化**这个窗口。这些需求需要码很多代码。但一些人已经写好了这些功能实现。因为这些需求在很多应用中重复出现了，在这里我们不需要重新写这些代码。PyQt5是一个高级工具套件，为我们封装了很多复杂功能的实现代码，我们可以更加简单的通过函数去实现这些功能。如果我们是在一个低级工具套件中写代码的话，下面例子的代码很有可能需要数百行来实现。


**001.py**
    #!/usr/bin/python3
    # -*- coding: utf-8 -*-

    """
    ZetCode PyQt5 教程
    在这个例子中, 我们用PyQt5创建了一个简单的窗口。

    作者: Jan Bodnar
    网站: zetcode.com 
    最后一次编辑: January 2015
    """

    import sys
    from PyQt5.QtWidgets import QApplication, QWidget


    if __name__ == '__main__':
        
        app = QApplication(sys.argv)

        w = QWidget()
        w.resize(250, 150)
        w.move(300, 300)
        w.setWindowTitle('Simple')
        w.show()
        
        sys.exit(app.exec_())
上面的代码示例会在屏幕上显示一个小窗口。
    import sys
    from PyQt5.QtWidgets import QApplication, QWidget
这里我们进行了一些必要模块的导入。最基础的widget组件位于PyQt5.QtWidget模块中
    app = QApplication(sys.argv)
所有的PyQt5应用必须创建一个应用（Application）对象。**sys.argv参数是一个来自命令行的参数列表。Python脚本可以在shell中运行。这是我们用来控制我们应用启动的一种方法。**
    w = QWidget()
Qwidget组件是PyQt5中所有用户界面类的基础类。我们给QWidget提供了默认的构造方法。默认构造方法没有父类。没有父类的widget组件将被作为窗口使用。
    w.resize(250, 150)
resize()方法调整了widget组件的大小。它现在是250px宽，150px高。
    w.move(300, 300)
move()方法移动widget组件到一个位置，这个位置是屏幕上x=300,y=300的坐标。
    w.setWindowTitle('Simple')
这里我们设置了我们窗口的标题。这个标题显示在标题栏中。
    w.show()
show()方法在屏幕上显示出widget。一个widget对象在这里第一次被在内存中创建，并且之后在屏幕上显示。
    sys.exit(app.exec_())
最后，应用进入主循环。在这个地方，事件处理开始执行。主循环用于接收来自窗口触发的事件，并且转发他们到widget应用上处理。如果我们调用exit()方法或主widget组件被销毁，主循环将退出。sys.exit()方法确保一个不留垃圾的退出。系统环境将会被通知应用是怎样被结束的。
exec_()方法有一个下划线。因为exec是Python保留关键字。因此，用exec_()来代替。

## SimpleFigure: Simple
一个简单的应用图标
应用图标是一个常常显示在标题栏左上方角落的小图片。在下面的例子里，我们将展示我们如何在PyQt5中显示应用图标。我们也将介绍一些新方法的使用。
**002.py**
    #!/usr/bin/python3
    # -*- coding: utf-8 -*-
    
    """
    ZetCode PyQt5 tutorial
    
    This example shows an icon
    in the titlebar of the window.
    
    author: Jan Bodnar
    website: zetcode.com
    last edited: January 2015
    """
    
    import sys
    from PyQt5.QtWidgets import QApplication, QWidget
    from PyQt5.QtGui import QIcon
    
    
    class Example(QWidget):
        
        def __init__(self):
            super().__init__()
            
            self.initUI()
            
            
        def initUI(self):
            
            self.setGeometry(300, 300, 300, 220)
            self.setWindowTitle('Icon')
            self.setWindowIcon(QIcon('web.png'))       
        
            self.show()
            
            
    if __name__ == '__main__':
        
        app = QApplication(sys.argv)
        ex = Example()
        sys.exit(app.exec_()) 
上述的例子使用传统的面向过程的代码风格。Python编程语言提供面向过程和面向对象的代码风格。PyQt5编程意味着就是面向对象的编程。
    class Example(QWidget):
        
        def __init__(self):
            super().__init__()
            ...
在面向对象编程中有三个重要的东西，分别是**类，数据和方法**。这里我们创建了一个新类叫做Example。Example类继承自QWidget类。这意味着我们调用了两个构造方法：第一个是Example类的构造方法，第二个是被继承类的构造方法。super()方法返回了Example类的父类对象，并且我们调用了父类的构造方法。__init__()方法是Python语言中的构造方法。
    self.initUI()
GUI的创建授予initUI()方法完成。
    self.setGeometry(300, 300, 300, 220)
    self.setWindowTitle('Icon')
    self.setWindowIcon(QIcon('web.png')) 
三个方法都继承自QWidgets类。setGeometry()做了两件事：将窗口在屏幕上显示，并设置了它的尺寸。setGeometry()方法的前两个参数定位了窗口的x轴和y轴位置。第三个参数是定义窗口的宽度，第四个参数是定义窗口的高度。事实上，这是将resize()和move()方法融合在一个方法内。为了做好这个例子，我们创建了一个QIcon对象。QIcon对象接收一个我们要显示的图片路径作为参数。
    if __name__ == '__main__':
        
        app = QApplication(sys.argv)
        ex = Example()
        sys.exit(app.exec_()) 
应用和example对象被创建。主循环被启动。


## IconFigure: Icon

显示一个提示文本
我们可以给我们的任何widget组件提供气泡帮助提示框。
**003.py**
    #!/usr/bin/python3
    # -*- coding: utf-8 -*-
    
    """
    ZetCode PyQt5 tutorial
    
    This example shows a tooltip on
    a window and a button.
    
    author: Jan Bodnar
    website: zetcode.com
    last edited: January 2015
    """
    
    import sys
    from PyQt5.QtWidgets import (QWidget, QToolTip,
        QPushButton, QApplication)
    from PyQt5.QtGui import QFont   
    
    
    class Example(QWidget):
        def __init__(self):
            super().__init__()
            self.initUI()
            
        def initUI(self):
            QToolTip.setFont(QFont('SansSerif', 10))
            self.setToolTip('This is a <b>QWidget</b> widget')
            btn = QPushButton('Button', self)
            btn.setToolTip('This is a <b>QPushButton</b> widget')
            btn.resize(btn.sizeHint())
            btn.move(50, 50)      
            
            self.setGeometry(300, 300, 300, 200)
            self.setWindowTitle('Tooltips')   
            self.show()
            
            
    if __name__ == '__main__':
        
        app = QApplication(sys.argv)
        ex = Example()
        sys.exit(app.exec_())

在这个例子中，我们为两个PyQt5组件显示了提示框。

    QToolTip.setFont(QFont('SansSerif', 10))

这个静态方法设置了用于提示框的字体。我们使用10px大小的SansSerif字体。

    self.setToolTip('This is a <b>QWidget</b> widget') 

为了创建提示框，我们调用了setTooltip()方法。我们可以在提示框中使用富文本格式。

    btn = QPushButton('Button', self)
    btn.setToolTip('This is a <b>QPushButton</b> widget')

我们创建了一个按钮组件并且为它设置一个提示框。

    btn.resize(btn.sizeHint())
    btn.move(50, 50)

这里改变了按钮的大小，并移动了在窗口上的位置。setHint()方法给了按钮一个推荐的大小。

    TooltipsFigure: Tooltips

关闭窗口
明显的关闭窗口的方法是点击标题栏的X标记。在下面的例子中，我们将展示怎么通过程序来关闭我们的窗口。我们将简单的触及信号和槽机制。

    QPushButton(string text, QWidget parent = None)

text参数是将显示在按钮中的内容。parent参数是一个用来放置我们按钮的组件。在我们的例子中将会是QWidget组件。一个应用的组件是分层结构的。在这个分层内，大多数组件都有父类。没有父类的组件是顶级窗口。

## 004.py

    #!/usr/bin/python3
    # -*- coding: utf-8 -*-
    
    """
    ZetCode PyQt5 tutorial
    
    This program creates a quit
    button. When we press the button,
    the application terminates.
    
    author: Jan Bodnar
    website: zetcode.com
    last edited: January 2015
    """
    
    import sys
    from PyQt5.QtWidgets import QWidget, QPushButton, QApplication
    from PyQt5.QtCore import QCoreApplication
    
    
    class Example(QWidget):
        
        def __init__(self):
            super().__init__()
            
            self.initUI()
            
            
        def initUI(self):              
            
            qbtn = QPushButton('Quit', self)
            qbtn.clicked.connect(QCoreApplication.instance().quit)
            qbtn.resize(qbtn.sizeHint())
            qbtn.move(50, 50)      
            
            self.setGeometry(300, 300, 250, 150)
            self.setWindowTitle('Quit button')   
            self.show()
     
    if __name__ == '__main__':
        
        app = QApplication(sys.argv)
        ex = Example()
        sys.exit(app.exec_())
 

在这个例子中，我们创建一个退出按钮，一旦按下按钮，应用将会结束。

    from PyQt5.QtCore import QCoreApplication

我们需要一个来自QtCore的对象模块。

    qbtn = QPushButton('Quit', self)

我们创建了一个按钮。按钮是一个QPushButton类的实例。构造方法的第一个参数是显示在button上的标签文本。第二个参数是父组件。父组件是Example组件，它继承了QWiget类。

    qbtn.clicked.connect(QCoreApplication.instance().quit)

在PyQt5中，事件处理系统由信号&槽机制建立。如果我们点击了按钮，信号clicked被发送。槽可以是Qt内置的槽或Python的一个方法调用。QCoreApplication类包含了主事件循环；它处理和转发所有事件。instance()方法给我们返回一个实例化对象。注意QCoreAppli类由QApplication创建。点击信号连接到quit()方法，将结束应用。事件通信在两个对象之间进行：发送者和接受者。发送者是按钮，接受者是应用对象。

Quit buttonFigure: Quit button

Message Box
默认的，如果我们点击了标题栏上的x按钮，QWidget会被关闭。又是我们希望修改这个默认动作。举个例子，如果我们有个文件在编辑器内打开，并且我们对这个文件做了一些修改。 我们显示一个message box来确认这个动作。

"""
ZetCode PyQt5 tutorial
 
This program shows a confirmation
message box when we click on the close
button of the application window.
 
author: Jan Bodnar
website: zetcode.com
last edited: January 2015
"""
 
import sys
from PyQt5.QtWidgets import QWidget, QMessageBox, QApplication
 
 
class Example(QWidget):
     
    def __init__(self):
        super().__init__()
         
        self.initUI()
         
         
    def initUI(self):              
         
        self.setGeometry(300, 300, 250, 150)       
        self.setWindowTitle('Message box')   
        self.show()
         
         
    def closeEvent(self, event):
         
        reply = QMessageBox.question(self, 'Message',
            "Are you sure to quit?", QMessageBox.Yes |
            QMessageBox.No, QMessageBox.No)
 
        if reply == QMessageBox.Yes:
            event.accept()
        else:
            event.ignore()       
         
         
if __name__ == '__main__':
     
    app = QApplication(sys.argv)
    ex = Example()
    sys.exit(app.exec_())
 

如果我们关闭一个QWidget，QCloseEvent类事件将被生成。要修改组件动作我们需要重新实现closeEvent()事件处理方法。

1
2
3
reply = QMessageBox.question(self, 'Message',
    "Are you sure to quit?", QMessageBox.Yes |
    QMessageBox.No, QMessageBox.No)
 

我们现实一个带两个按钮的message box：YES和No按钮。代码中第一个字符串的内容被显示在标题栏上。第二个字符串是对话框上显示的文本。第三个参数指定了显示在对话框上的按钮集合。最后一个参数是默认选中的按钮。这个按钮一开始就获得焦点。返回值被储存在reply变量中。

1
2
3
4
if reply == QtGui.QMessageBox.Yes:
    event.accept()
else:
    event.ignore()
 

在这里我们测试一下返回值。代码逻辑是如果我们点击Yes按钮，我们接收到的事件关闭事件，这将导致了组件的关闭和应用的结束。否则不是点击Yes按钮的话我们将忽略将关闭事件。

Message boxFigure: Message box

屏幕上的居中窗口
下面的脚本展示我们如何把窗口居中显示到桌面窗口。

1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
48
#!/usr/bin/python3
# -*- coding: utf-8 -*-
 
"""
ZetCode PyQt5 tutorial
 
This program centers a window
on the screen.
 
author: Jan Bodnar
website: zetcode.com
last edited: January 2015
"""
 
import sys
from PyQt5.QtWidgets import QWidget, QDesktopWidget, QApplication
 
 
class Example(QWidget):
     
    def __init__(self):
        super().__init__()
         
        self.initUI()
         
         
    def initUI(self):              
         
        self.resize(250, 150)
        self.center()
         
        self.setWindowTitle('Center')   
        self.show()
         
         
    def center(self):
         
        qr = self.frameGeometry()
        cp = QDesktopWidget().availableGeometry().center()
        qr.moveCenter(cp)
        self.move(qr.topLeft())
         
         
if __name__ == '__main__':
     
    app = QApplication(sys.argv)
    ex = Example()
    sys.exit(app.exec_()) 
 

QtGui.QDesktopWidget类提供了我们桌面窗口的信息，包含了屏幕尺寸。

1
self.center()
 

将窗口居中放置的代码在自定义的center()方法中。

1
qr = self.frameGeometry()
 

我们获得主窗口的一个矩形特定几何图形。这包含了窗口的框架。

1
cp = QDesktopWidget().availableGeometry().center()
 

我们算出相对于显示器的绝对值。并且从这个绝对值中，我们获得了屏幕中心点。

1
qr.moveCenter(cp)
 

我们的矩形已经设置好了它的宽和高。现在我们把矩形的中心设置到屏幕的中间去。矩形的大小并不会改变。

1
self.move(qr.topLeft())
 

我们移动了应用窗口的左上方的点到qr矩形的左上方的点，因此居中显示在我们的屏幕上。
这是PyQt5教程的一部分，这部分涵盖了一些基础知识。