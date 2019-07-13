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
这是一个显示一个小窗口的简单例子。我们可以做许多这样的窗口。我们可以调整它的**窗口尺寸，最大化或最小化**这个窗口。这些需求需要码很多代码。但一些人已经写好了这些功能实现。因为这些需求在很多应用中重复出现了，在这里我们不需要重新写这些代码。
PyQt5是一个高级工具套件，为我们封装了很多复杂功能的实现代码，我们可以更加简单的通过函数去实现这些功能。如果我们是在一个低级工具套件中写代码的话，下面例子的代码很有可能需要数百行来实现。

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

最后，应用进入主循环。在这个地方，事件处理开始执行。主循环用于接收来自窗口触发的事件，并且转发他们到widget应用上处理。如果我们调用exit()方法或主widget组件被销毁，主循环将退出。sys.exit()方法确保一个不留垃圾的退出。系统环境将会被通 知应用是怎样被结束的。

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

## Message Box
默认的，如果我们点击了标题栏上的x按钮，QWidget会被关闭。又是我们希望修改这个默认动作。举个例子，如果我们有个文件在编辑器内打开，并且我们对这个文件做了一些修改。 我们显示一个message box来确认这个动作。
**005.py**
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


    reply = QMessageBox.question(self, 'Message',
        "Are you sure to quit?", QMessageBox.Yes |
        QMessageBox.No, QMessageBox.No)
 

我们现实一个带两个按钮的message box：YES和No按钮。代码中第一个字符串的内容被显示在标题栏上。第二个字符串是对话框上显示的文本。第三个参数指定了显示在对话框上的按钮集合。最后一个参数是默认选中的按钮。这个按钮一开始就获得焦点。返回值被储存在reply变量中。

    if reply == QtGui.QMessageBox.Yes:
        event.accept()
    else:
        event.ignore()

在这里我们测试一下返回值。代码逻辑是如果我们点击Yes按钮，我们接收到的事件关闭事件，这将导致了组件的关闭和应用的结束。否则不是点击Yes按钮的话我们将忽略将关闭事件。

Message boxFigure: Message box

## 屏幕上的居中窗口
下面的脚本展示我们如何把窗口居中显示到桌面窗口。
**006.py**
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
 

QtGui.QDesktopWidget类提供了我们**桌面窗口的信息**，包含了屏幕尺寸。

    self.center() 

将窗口居中放置的代码在自定义的center()方法中。

    qr = self.frameGeometry()

我们获得主窗口的一个矩形特定几何图形。这包含了窗口的框架。

    cp = QDesktopWidget().availableGeometry().center()

我们算出相对于显示器的绝对值。并且从这个绝对值中，我们获得了屏幕中心点。

    qr.moveCenter(cp)

我们的矩形已经设置好了它的宽和高。现在我们把矩形的中心设置到屏幕的中间去。矩形的大小并不会改变。

    self.move(qr.topLeft())

我们移动了应用窗口的左上方的点到qr矩形的左上方的点，因此居中显示在我们的屏幕上。
这是PyQt5教程的一部分，这部分涵盖了一些基础知识。

# PyQt5中的菜单和工具栏
在这部分的PyQt5教程中，我们将创建菜单和工具栏。菜单式位于菜单栏的一组命令操作。工具栏是应用窗体中由按钮和一些常规命令操作组成的组件。

## 主窗口
QMainWindow类提供了一个应用主窗口。默认创建一个拥有状态栏、工具栏和菜单栏的经典应用窗口骨架。

## 状态栏
状态栏是用来显示状态信息的组件。
**007.py**
    #!/usr/bin/python3
    # -*- coding: utf-8 -*-
    
    """
    ZetCode PyQt5 tutorial
    
    This program creates a statusbar.
    
    author: Jan Bodnar
    website: zetcode.com
    last edited: January 2015
    """
    
    import sys
    from PyQt5.QtWidgets import QMainWindow, QApplication
    
    
    class Example(QMainWindow):
        
        def __init__(self):
            super().__init__()
            
            self.initUI()
            
            
        def initUI(self):              
            
            self.statusBar().showMessage('Ready')
            
            self.setGeometry(300, 300, 250, 150)
            self.setWindowTitle('Statusbar')   
            self.show()
    
    
    if __name__ == '__main__':
        
        app = QApplication(sys.argv)
        ex = Example()
        sys.exit(app.exec_())
状态栏由QMainWindow组件帮助创建完成（依赖于QMainWindow组件）。

    self.statusBar().showMessage('Ready')
为了得到状态栏，我们调用了QtGui.QMainWindow类的statusBar()方法。第一次调用这个方法创建了一个状态栏。随后方法返回状态栏对象。然后用showMessage()方法在状态栏上显示一些信息。

菜单栏
菜单栏是GUI应用的常规组成部分。是位于各种菜单中的一组命令操作（Mac OS 对待菜单栏有些不同。为了获得全平台一致的效果，我们可以在代码中加入一行：menubar.setNativeMenuBar(False)）。

    #!/usr/bin/python3
    # -*- coding: utf-8 -*-
    
    """
    ZetCode PyQt5 tutorial
    
    This program creates a menubar. The
    menubar has one menu with an exit action.
    
    author: Jan Bodnar
    website: zetcode.com
    last edited: January 2015
    """
    
    import sys
    from PyQt5.QtWidgets import QMainWindow, QAction, qApp, QApplication
    from PyQt5.QtGui import QIcon
    
    
    class Example(QMainWindow):
        
        def __init__(self):
            super().__init__()
            
            self.initUI()
            
            
        def initUI(self):              
            
            exitAction = QAction(QIcon('exit.png'), '&Exit', self)       
            exitAction.setShortcut('Ctrl+Q')
            exitAction.setStatusTip('Exit application')
            exitAction.triggered.connect(qApp.quit)
    
            self.statusBar()
    
            menubar = self.menuBar()
            fileMenu = menubar.addMenu('&File')
            fileMenu.addAction(exitAction)
            
            self.setGeometry(300, 300, 300, 200)
            self.setWindowTitle('Menubar')   
            self.show()
            
            
    if __name__ == '__main__':
        
        app = QApplication(sys.argv)
        ex = Example()
        sys.exit(app.exec_())
 

在上面的例子中，我们创建了有一个菜单项的菜单栏。这个菜单项包含一个选中后中断应用的动作。

    exitAction = QAction(QIcon('exit.png'), '&Exit', self)       
    exitAction.setShortcut('Ctrl+Q')
    exitAction.setStatusTip('Exit application')

QAction是一个用于菜单栏、工具栏或自定义快捷键的抽象动作行为。在上面的三行中，我们创建了一个有指定图标和文本为'Exit'的标签。另外，还为这个动作定义了一个快捷键。第三行创建一个当我们鼠标浮于菜单项之上就会显示的一个状态提示。


    exitAction.triggered.connect(qApp.quit)
当我们选中特定的动作，一个触发信号会被发射。信号连接到QApplication组件的quit()方法。这样就中断了应用。

    menubar = self.menuBar()
    fileMenu = menubar.addMenu('&File')
    fileMenu.addAction(exitAction)
menuBar()方法创建了一个菜单栏。我们创建一个file菜单，然后将退出动作添加到file菜单中。

## 工具栏
菜单可以集成所有命令，这样我们可以在应用中使用这些被集成的命令。工具栏提供了一个快速访问常用命令的方式。
**009.py**
    #!/usr/bin/python3
    # -*- coding: utf-8 -*-
    
    """
    ZetCode PyQt5 tutorial
    
    This program creates a toolbar.
    The toolbar has one action, which
    terminates the application, if triggered.
    
    author: Jan Bodnar
    website: zetcode.com
    last edited: January 2015
    """
    
    import sys
    from PyQt5.QtWidgets import QMainWindow, QAction, qApp, QApplication
    from PyQt5.QtGui import QIcon
    
    
    class Example(QMainWindow):
        
        def __init__(self):
            super().__init__()
            
            self.initUI()
            
            
        def initUI(self):              
            
            exitAction = QAction(QIcon('exit24.png'), 'Exit', self)
            exitAction.setShortcut('Ctrl+Q')
            exitAction.triggered.connect(qApp.quit)
            
            self.toolbar = self.addToolBar('Exit')
            self.toolbar.addAction(exitAction)
            
            self.setGeometry(300, 300, 300, 200)
            self.setWindowTitle('Toolbar')   
            self.show()
            
            
    if __name__ == '__main__':
        
        app = QApplication(sys.argv)
        ex = Example()
        sys.exit(app.exec_())
 

上述例子中，我们创建了一个简单的工具栏。工具栏有一个动作，当这个退出动作被触发时应用将会被中断。

    exitAction = QAction(QIcon('exit24.png'), 'Exit', self)
    exitAction.setShortcut('Ctrl+Q')
    exitAction.triggered.connect(qApp.quit)
 

我们创建了一个动作对象，和之前菜单栏中的部分代码相似。这个动作有一个标签，图标和快捷键。并且将QtGui.QMainWindow的quit()方法连接到了触发信号上。

    self.toolbar = self.addToolBar('Exit')
    self.toolbar.addAction(exitAction)
 

这里我们创建了一个工具栏，并且在其中插入一个动作对象。

ToolbarFigure: Toolbar

将几个组件放在一起使用
在上面的例子中，我们创建了菜单栏、工具栏和状态栏。下面我们将创建一个中心组件。
**010.py**
    #!/usr/bin/python3
    # -*- coding: utf-8 -*-
    
    """
    ZetCode PyQt5 tutorial
    
    This program creates a skeleton of
    a classic GUI application with a menubar,
    toolbar, statusbar, and a central widget.
    
    author: Jan Bodnar
    website: zetcode.com
    last edited: January 2015
    """
    
    import sys
    from PyQt5.QtWidgets import QMainWindow, QTextEdit, QAction, QApplication
    from PyQt5.QtGui import QIcon
    
    
    class Example(QMainWindow):
        
        def __init__(self):
            super().__init__()
            
            self.initUI()
            
            
        def initUI(self):              
            
            textEdit = QTextEdit()
            self.setCentralWidget(textEdit)
    
            exitAction = QAction(QIcon('exit24.png'), 'Exit', self)
            exitAction.setShortcut('Ctrl+Q')
            exitAction.setStatusTip('Exit application')
            exitAction.triggered.connect(self.close)
    
            self.statusBar()
    
            menubar = self.menuBar()
            fileMenu = menubar.addMenu('&File')
            fileMenu.addAction(exitAction)
    
            toolbar = self.addToolBar('Exit')
            toolbar.addAction(exitAction)
            
            self.setGeometry(300, 300, 350, 250)
            self.setWindowTitle('Main window')   
            self.show()
            
            
    if __name__ == '__main__':
        
        app = QApplication(sys.argv)
        ex = Example()
        sys.exit(app.exec_())
 

事例代码创建了一个带有菜单栏、工具栏和状态栏的经典GUI应用骨架。

    textEdit = QTextEdit()
    self.setCentralWidget(textEdit)
 

在这里我们创建了一个文本编辑框组件。我们将它设置成QMainWindow的中心组件。中心组件占据了所有剩下的空间。

Main windowFigure: Main window

在这个部分的PyQt5教程中，我们使用了菜单、工具栏、状态栏和一个应用主窗口。

PyQt5中的布局管理
布局管理是GUI编程中的一个重要方面。布局管理是一种如何在应用窗口上防止组件的一种方法。我们可以通过两种基础方式来管理布局。我们可以使用绝对定位和布局类。

绝对定位
程序指定了组件的位置并且每个组件的大小用像素作为单位来丈量。当你使用了绝对定位，我们需要知道下面的几点限制：

-   如果我们改变了窗口大小，组件的位置和大小并不会发生改变。
-   在不同平台上，应用的外观可能不同
-   改变我们应用中的字体的话可能会把应用弄得一团糟。
-   如果我们决定改变我们的布局，我们必须完全重写我们的布局，这样非常乏味和浪费时间。
-   下面的例子中，使用了绝对坐标来定位组件

**011.py**

    #!/usr/bin/python3
    # -*- coding: utf-8 -*-
 
    """
    ZetCode PyQt5 tutorial
    
    This example shows three labels on a window
    using absolute positioning.
    
    author: Jan Bodnar
    website: zetcode.com
    last edited: January 2015
    """
    
    import sys
    from PyQt5.QtWidgets import QWidget, QLabel, QApplication
    
    
    class Example(QWidget):
        
        def __init__(self):
            super().__init__()
            
            self.initUI()
            
            
        def initUI(self):
            
            lbl1 = QLabel('Zetcode', self)
            lbl1.move(15, 10)
    
            lbl2 = QLabel('tutorials', self)
            lbl2.move(35, 40)
            
            lbl3 = QLabel('for programmers', self)
            lbl3.move(55, 70)       
            
            self.setGeometry(300, 300, 250, 150)
            self.setWindowTitle('Absolute')   
            self.show()
            
            
    if __name__ == '__main__':
        
        app = QApplication(sys.argv)
        ex = Example()
        sys.exit(app.exec_())
　　

我们使用move()方法来定位我们的组件。在上面的例子中我们使用move()方法定位了一些标签组件。在使用move()方法时，我们给move()方法提供了x和y坐标作为参数。move()使用的坐标系统是从左上角开始计算的。x值从左到右增长。y值从上到下增长。


    lbl1 = QLabel('Zetcode', self)
    lbl1.move(15, 10)
　　

将标签组件定位在x=15，y=10的坐标位置。

Absolute positioningFigure: Absolute positioning

## 箱布局
布局管理器的布局管理类非常灵活，实用。它是将组件定位在窗口上的首选方式。QHBoxLayout和QVBoxLayout是两个基础布局管理类，他们水平或垂直的线性排列组件。想象一下我们需要在右下角排列两个按钮。为了使用箱布局，我们将使用一个水平箱布局和垂直箱布局来实现。同样为了使用一些必要的空白，我们将添加一些拉伸因子。
**012.py**
    #!/usr/bin/python3
    # -*- coding: utf-8 -*-
    
    """
    ZetCode PyQt5 tutorial
    
    In this example, we position two push
    buttons in the bottom-right corner
    of the window.
    
    author: Jan Bodnar
    website: zetcode.com
    last edited: January 2015
    """
    
    import sys
    from PyQt5.QtWidgets import (QWidget, QPushButton,
        QHBoxLayout, QVBoxLayout, QApplication)
    
    
    class Example(QWidget):
        
        def __init__(self):
            super().__init__()
            
            self.initUI()
            
            
        def initUI(self):
            
            okButton = QPushButton("OK")
            cancelButton = QPushButton("Cancel")
    
            hbox = QHBoxLayout()
            hbox.addStretch(1)
            hbox.addWidget(okButton)
            hbox.addWidget(cancelButton)
    
            vbox = QVBoxLayout()
            vbox.addStretch(1)
            vbox.addLayout(hbox)
            
            self.setLayout(vbox)   
            
            self.setGeometry(300, 300, 300, 150)
            self.setWindowTitle('Buttons')   
            self.show()
            
            
    if __name__ == '__main__':
        
        app = QApplication(sys.argv)
        ex = Example()
        sys.exit(app.exec_())
　　

例子在右下角放置了两个按钮。当我们改变应用窗口大小时，它们会相对于应用窗口不改变位置。在这个例子中我们使用了QHBoxLayout和QVBoxLayout两个布局类。

    okButton = QPushButton("OK")
    cancelButton = QPushButton("Cancel")
　　

在这里我们创建了两个按钮。

    hbox = QHBoxLayout()
    hbox.addStretch(1)
    hbox.addWidget(okButton)
    hbox.addWidget(cancelButton)
　　
这里我们创建了一个水平箱布局，并且增加了一个**拉伸因子**和**两个按钮**。拉伸因子在两个按钮之前增加了一个可伸缩空间。这会将按钮推到窗口的右边。

    vbox = QVBoxLayout()
    vbox.addStretch(1)
    vbox.addLayout(hbox)
　　

为了创建必要的布局，我们把水平布局放置在垂直布局内。拉伸因子将把包含两个按钮的水平箱布局推到窗口的底边。

    self.setLayout(vbox)

最后，我们设置一下窗口的主布局。


## ButtonsFigure: Buttons 网格布局
最常用的布局类是网格布局。这个布局使用行了列分割空间。要创建一个网格布局，我们需要使用QGridLayout类。
**013.py**

    #!/usr/bin/python3
    # -*- coding: utf-8 -*-
    
    """
    ZetCode PyQt5 tutorial
    
    In this example, we create a skeleton
    of a calculator using a QGridLayout.
    
    author: Jan Bodnar
    website: zetcode.com
    last edited: January 2015
    """
    
    import sys
    from PyQt5.QtWidgets import (QWidget, QGridLayout,
        QPushButton, QApplication)
    
    
    class Example(QWidget):
        
        def __init__(self):
            super().__init__()
            
            self.initUI()
            
            
        def initUI(self):
            
            grid = QGridLayout()
            self.setLayout(grid)
    
            names = ['Cls', 'Bck', '', 'Close',
                    '7', '8', '9', '/',
                    '4', '5', '6', '*',
                    '1', '2', '3', '-',
                    '0', '.', '=', '+']
            
            positions = [(i,j) for i in range(5) for j in range(4)]
            
            for position, name in zip(positions, names):
                
                if name == '':
                    continue
                button = QPushButton(name)
                grid.addWidget(button, *position)
                
            self.move(300, 150)
            self.setWindowTitle('Calculator')
            self.show()
            
            
    if __name__ == '__main__':
        
        app = QApplication(sys.argv)
        ex = Example()
        sys.exit(app.exec_())
　　

在我们的例子中，我们创建了一个全是按钮的网格布局。

    grid = QGridLayout()
    self.setLayout(grid)

实例化QGridLayout类，并且把这个类设为应用窗口的布局。


    names = ['Cls', 'Bck', '', 'Close',
                '7', '8', '9', '/',
            '4', '5', '6', '*',
                '1', '2', '3', '-',
            '0', '.', '=', '+']
这些标签会在之后的按钮中使用。

    positions = [(i,j) for i in range(5) for j in range(4)]
我们创建了一个网格的定位列表。

    for position, name in zip(positions, names):
     
        if name == '':
            continue
        button = QPushButton(name)
        grid.addWidget(button, *position)
创建出按钮组件，并使用addWidget()方法向布局中添加按钮。

Calculator skeletonFigure: Calculator skeleton

## 文本审阅窗口示例

在网格中，组件可以跨多列或多行。在这个例子中，我们对它进行一下说明。

    #!/usr/bin/python3
    # -*- coding: utf-8 -*-
    
    """
    ZetCode PyQt5 tutorial
    
    In this example, we create a bit
    more complicated window layout using
    the QGridLayout manager.
    
    author: Jan Bodnar
    website: zetcode.com
    last edited: January 2015
    """
    
    import sys
    from PyQt5.QtWidgets import (QWidget, QLabel, QLineEdit,
        QTextEdit, QGridLayout, QApplication)
    
    
    class Example(QWidget):
        
        def __init__(self):
            super().__init__()
            
            self.initUI()
            
            
        def initUI(self):
            
            title = QLabel('Title')
            author = QLabel('Author')
            review = QLabel('Review')
    
            titleEdit = QLineEdit()
            authorEdit = QLineEdit()
            reviewEdit = QTextEdit()
    
            grid = QGridLayout()
            grid.setSpacing(10)
    
            grid.addWidget(title, 1, 0)
            grid.addWidget(titleEdit, 1, 1)
    
            grid.addWidget(author, 2, 0)
            grid.addWidget(authorEdit, 2, 1)
    
            grid.addWidget(review, 3, 0)
            grid.addWidget(reviewEdit, 3, 1, 5, 1)
            
            self.setLayout(grid)
            
            self.setGeometry(300, 300, 350, 300)
            self.setWindowTitle('Review')   
            self.show()
            
            
    if __name__ == '__main__':
        
        app = QApplication(sys.argv)
        ex = Example()
        sys.exit(app.exec_())
我们创建了包含三个标签，两个单行编辑框和一个文本编辑框组件的窗口。布局使用了QGridLayout布局。

    grid = QGridLayout()
    grid.setSpacing(10)
我们创建了一个网格布局并且设置了组件之间的间距。
    grid.addWidget(reviewEdit, 3, 1, 5, 1)
如果我们向网格布局中增加一个组件，我们可以提供组件的跨行和跨列参数。在这个例子中，我们让reviewEdit组件跨了5行。
    void QGridLayout::addWidget(QWidget * widget, int fromRow, int fromColumn, int rowSpan, int columnSpan, Qt::Alignment alignment = 0)
    This is an overloaded function.

Review exampleFigure: Review example

这部分的PyQt5教程专门用于讲述布局管理。

PyQt5中的事件和信号
在这部分PyQt5编程教程中，我们探索应用中事件和信号的发生。

事件
所有的GUI应用都是**事件**驱动的。事件主要由应用的**用户操作**产生的。但是事件可能由其他条件触发，比如：一个网络连接，一个窗口管理器，一个定时器，这些动作都可能触发事件的产生。当我们调用应用的exec_()方法时，应用进入了主循环。主循环用于检测事件的产生并且将事件送到用于处理的对象中去。

在事件模型，有三个参与者

- 事件源
- 事件对象
- 事件目标
事件源是状态发生改变的对象。它产生了事件。事件对象(evnet)封装了事件源中的状态变化。事件目标是想要被通知的对象。事件源对象代表了处理一个事件直到事件目标做出响应的任务。

PyQt5有一个独一无二的信号和槽机制来处理事件。信号和槽用于对象之间的通信。当指定事件发生，一个事件信号会被发射。槽可以被任何Python脚本调用。当和槽连接的信号被发射时，槽会被调用。

## 信号 & 槽
这个例子演示了PyQt5中的信号和槽的使用。

    #!/usr/bin/python3
    # -*- coding: utf-8 -*-
    
    """
    ZetCode PyQt5 tutorial
    
    In this example, we connect a signal
    of a QSlider to a slot of a QLCDNumber.
    
    author: Jan Bodnar
    website: zetcode.com
    last edited: January 2015
    """
    
    import sys
    from PyQt5.QtCore import Qt
    from PyQt5.QtWidgets import (QWidget, QLCDNumber, QSlider,
        QVBoxLayout, QApplication)
    
    
    class Example(QWidget):
        
        def __init__(self):
            super().__init__()
            
            self.initUI()
            
            
        def initUI(self):
            
            lcd = QLCDNumber(self)
            sld = QSlider(Qt.Horizontal, self)
    
            vbox = QVBoxLayout()
            vbox.addWidget(lcd)
            vbox.addWidget(sld)
    
            self.setLayout(vbox)
            sld.valueChanged.connect(lcd.display)
            
            self.setGeometry(300, 300, 250, 150)
            self.setWindowTitle('Signal & slot')
            self.show()
            
    
    if __name__ == '__main__':
        
        app = QApplication(sys.argv)
        ex = Example()
        sys.exit(app.exec_())
　　

在我们的例子中，我们显示了一个QtGui.QLCDNumber和一个QtGui.QSlider类。我们拖动滑块条的把手，lcd数字会变化。

    sld.valueChanged.connect(lcd.display)
　　

这里，我们将滑块条的valueChanged信号和lcd数字显示的display槽连接在一起。

发送者是一个发送了信号的对象。接受者是一个接受了信号的对象。槽是对信号做出反应的方法。

## Signal & slotFigure: Signal & slot

重写事件处理函数
PyQt中的事件处理通常通过重写事件处理函数来处理。

    #!/usr/bin/python3
    # -*- coding: utf-8 -*-
    
    """
    ZetCode PyQt5 tutorial
    
    In this example, we reimplement an
    event handler.
    
    author: Jan Bodnar
    website: zetcode.com
    last edited: January 2015
    """
    
    import sys
    from PyQt5.QtCore import Qt
    from PyQt5.QtWidgets import QWidget, QApplication
    
    
    class Example(QWidget):
        
        def __init__(self):
            super().__init__()
            
            self.initUI()
            
            
        def initUI(self):     
            
            self.setGeometry(300, 300, 250, 150)
            self.setWindowTitle('Event handler')
            self.show()
            
            
        def keyPressEvent(self, e):
            
            if e.key() == Qt.Key_Escape:
                self.close()
            
            
    if __name__ == '__main__':
        
        app = QApplication(sys.argv)
        ex = Example()
        sys.exit(app.exec_())

在我们的例子中，我们重写了keyPressEvent()事件处理函数。

    def keyPressEvent(self, e):
        
        if e.key() == Qt.Key_Escape:
            self.close()


如果我们点击了Esc按钮，应用将会被终止。

事件发送者
有时需要方便的知道哪一个组件是信号发送者。因此，PyQt5拥有了sender()方法来解决这个问题。
**017.py**

    #!/usr/bin/python3
    # -*- coding: utf-8 -*-
    
    """
    ZetCode PyQt5 tutorial
    
    In this example, we determine the event sender
    object.
    
    author: Jan Bodnar
    website: zetcode.com
    last edited: January 2015
    """
    import sys
    from PyQt5.QtWidgets import QMainWindow, QPushButton, QApplication
    
    class Example(QMainWindow):
        
        def __init__(self):
            super().__init__()
            
            self.initUI()
            
            
        def initUI(self):     
    
            btn1 = QPushButton("Button 1", self)
            btn1.move(30, 50)
    
            btn2 = QPushButton("Button 2", self)
            btn2.move(150, 50)
        
            btn1.clicked.connect(self.buttonClicked)           
            btn2.clicked.connect(self.buttonClicked)
            
            self.statusBar()
            
            self.setGeometry(300, 300, 290, 150)
            self.setWindowTitle('Event sender')
            self.show()
            
            
        def buttonClicked(self):
        
            sender = self.sender()
            self.statusBar().showMessage(sender.text() + ' was pressed')
         
         
    if __name__ == '__main__':
        
        app = QApplication(sys.argv)
        ex = Example()
        sys.exit(app.exec_())
在我们的例子中，我们有两个按钮。在buttonClikced()方法中，我们调用sender()方法来判断哪一个按钮是我们按下的。

    btn1.clicked.connect(self.buttonClicked)           
    btn2.clicked.connect(self.buttonClicked)
两个按钮都连接到了同一个槽中。

def buttonClicked(self):
   
    sender = self.sender()
    self.statusBar().showMessage(sender.text() + ' was pressed')
我们调用sender()方法判断发送信号的信号源是哪一个。然后在应用的状态栏上显示被按下的按钮的标签内容。

## Event senderFigure: Event sender

发送信号
从QObejct生成的对象可以发送信号。在下面的例子中我们将会看到怎样去发送自定义的信号。

    #!/usr/bin/python3
    # -*- coding: utf-8 -*-
    
    """
    ZetCode PyQt5 tutorial
    
    In this example, we show how to emit a
    signal.
    
    author: Jan Bodnar
    website: zetcode.com
    last edited: January 2015
    """
    
    import sys
    from PyQt5.QtCore import pyqtSignal, QObject
    from PyQt5.QtWidgets import QMainWindow, QApplication
    
    
    class Communicate(QObject):
        
        closeApp = pyqtSignal()
        
    
    class Example(QMainWindow):
        
        def __init__(self):
            super().__init__()
            
            self.initUI()
            
            
        def initUI(self):     
    
            self.c = Communicate()
            self.c.closeApp.connect(self.close)      
            
            self.setGeometry(300, 300, 290, 150)
            self.setWindowTitle('Emit signal')
            self.show()
            
            
        def mousePressEvent(self, event):
            
            self.c.closeApp.emit()
            
            
    if __name__ == '__main__':
        
        app = QApplication(sys.argv)
        ex = Example()
        sys.exit(app.exec_())
我们创建一个新的信号叫做closeApp。当触发鼠标点击事件时信号会被发射。信号连接到了QMainWindow的close()方法。

    class Communicate(QObject):
        
        closeApp = pyqtSignal()
信号使用了pyqtSignal()方法创建，并且成为外部类Communicate类的属性。


    self.c = Communicate()
    self.c.closeApp.connect(self.close)
把自定义的closeApp信号连接到QMainWindow的close()槽上。

    def mousePressEvent(self, event):
        
        self.c.closeApp.emit()
当我们在窗口上点击一下鼠标，closeApp信号会被发射。应用中断。

 

这部分的PyQt5教程中，我们概览了信号了槽机制。

## PyQt5中的对话框
对话框窗口或对话框是大多数主流GUI应用不可缺少的部分。对话是两个或更多人之间的会话。在计算机应用中，对话框是一个用来和应用对话的窗口。对话框可以用来输入数据，修改数据，改变应用设置等等。

 
## 输入对话框
QInputDialog提供了一个简单便利的对话框用于从用户那儿获得只一个值。输入值可以是字符串，数字，或者一个列表中的列表项。
**019.py**
    #!/usr/bin/python3
    # -*- coding: utf-8 -*-
    
    """
    ZetCode PyQt5 tutorial
    
    In this example, we receive data from
    a QInputDialog dialog.
    
    author: Jan Bodnar
    website: zetcode.com
    last edited: January 2015
    """
    
    import sys
    from PyQt5.QtWidgets import (QWidget, QPushButton, QLineEdit,
        QInputDialog, QApplication)
    
    
    class Example(QWidget):
        
        def __init__(self):
            super().__init__()
            
            self.initUI()
            
            
        def initUI(self):     
    
            self.btn = QPushButton('Dialog', self)
            self.btn.move(20, 20)
            self.btn.clicked.connect(self.showDialog)
            
            self.le = QLineEdit(self)
            self.le.move(130, 22)
            
            self.setGeometry(300, 300, 290, 150)
            self.setWindowTitle('Input dialog')
            self.show()
            
            
        def showDialog(self):
            
            text, ok = QInputDialog.getText(self, 'Input Dialog',
                'Enter your name:')
            
            if ok:
                self.le.setText(str(text))
            
            
    if __name__ == '__main__':
        
        app = QApplication(sys.argv)
        ex = Example()
        sys.exit(app.exec_())
例子中有一个按钮和一个单行编辑框组件。按下按钮会显示输入对话框用于获得一个字符串值。在对话框中输入的值会在单行编辑框组件中显示。

    text, ok = QInputDialog.getText(self, 'Input Dialog',
        'Enter your name:')

这一行会显示一个输入对话框。第一个字符串参数是对话框的标题，第二个字符串参数是对话框内的消息文本。对话框返回输入的文本内容和一个布尔值。如果我们点击了Ok按钮，布尔值就是true，反之布尔值是false（译者注：也只有按下Ok按钮时，返回的文本内容才会有值）。

    if ok:
        self.le.setText(str(text))

把我们从对话框接收到的文本设置到单行编辑框组件上显示。

## Input dialogFigure: Input dialog

颜色选择对话框
QColorDialog类提供了一个用于选择颜色的对话框组件。
**020.py**

    #!/usr/bin/python3
    # -*- coding: utf-8 -*-
    
    """
    ZetCode PyQt5 tutorial
    
    In this example, we select a color value
    from the QColorDialog and change the background
    color of a QFrame widget.
    
    author: Jan Bodnar
    website: zetcode.com
    last edited: January 2015
    """
    
    import sys
    from PyQt5.QtWidgets import (QWidget, QPushButton, QFrame,
        QColorDialog, QApplication)
    from PyQt5.QtGui import QColor
    
    
    class Example(QWidget):
        
        def __init__(self):
            super().__init__()
            
            self.initUI()
            
            
        def initUI(self):     
    
            col = QColor(0, 0, 0)
    
            self.btn = QPushButton('Dialog', self)
            self.btn.move(20, 20)
    
            self.btn.clicked.connect(self.showDialog)
    
            self.frm = QFrame(self)
            self.frm.setStyleSheet("QWidget { background-color: %s }"
                % col.name())
            self.frm.setGeometry(130, 22, 100, 100)           
            
            self.setGeometry(300, 300, 250, 180)
            self.setWindowTitle('Color dialog')
            self.show()
            
            
        def showDialog(self):
        
            col = QColorDialog.getColor()
    
            if col.isValid():
                self.frm.setStyleSheet("QWidget { background-color: %s }"
                    % col.name())
                
            
    if __name__ == '__main__':
        
        app = QApplication(sys.argv)
        ex = Example()
        sys.exit(app.exec_())

例子中显示了一个按钮和一个QFrame。将QFrame组件的背景设置为黑色。使用颜色选择框类，我们可以改变它的颜色。

    col = QColor(0, 0, 0)
初始化QtGuiQFrame组件的背景颜色。

    col = QColorDialog.getColor()
这一行弹出颜色选择框。

    if col.isValid():
        self.frm.setStyleSheet("QWidget { background-color: %s }"
            % col.name())
如果我们选中一个颜色并且点了ok按钮，会返回一个有效的颜色值。如果我们点击了Cancel按钮，不会返回选中的颜色值。我们使用样式表来定义背景颜色。

## 字体选择框
QFontDialog是一个用于选择字体的对话框组件。

 
    #!/usr/bin/python3
    # -*- coding: utf-8 -*-
    
    """
    ZetCode PyQt5 tutorial
    
    In this example, we select a font name
    and change the font of a label.
    
    author: Jan Bodnar
    website: zetcode.com
    last edited: January 2015
    """
    
    import sys
    from PyQt5.QtWidgets import (QWidget, QVBoxLayout, QPushButton,
        QSizePolicy, QLabel, QFontDialog, QApplication)
    
    
    class Example(QWidget):
        
        def __init__(self):
            super().__init__()
            
            self.initUI()
            
            
        def initUI(self):     
    
            vbox = QVBoxLayout()
    
            btn = QPushButton('Dialog', self)
            btn.setSizePolicy(QSizePolicy.Fixed,
                QSizePolicy.Fixed)
            
            btn.move(20, 20)
    
            vbox.addWidget(btn)
    
            btn.clicked.connect(self.showDialog)
            
            self.lbl = QLabel('Knowledge only matters', self)
            self.lbl.move(130, 20)
    
            vbox.addWidget(self.lbl)
            self.setLayout(vbox)         
            
            self.setGeometry(300, 300, 250, 180)
            self.setWindowTitle('Font dialog')
            self.show()
            
            
        def showDialog(self):
    
            font, ok = QFontDialog.getFont()
            if ok:
                self.lbl.setFont(font)
            
            
    if __name__ == '__main__':
        
        app = QApplication(sys.argv)
        ex = Example()
        sys.exit(app.exec_())
在我们的例子中，我们有一个按钮和一个表情。通过字体选择对话框，我们可以改变标签的字体。

    font, ok = QFontDialog.getFont()
在这儿我们弹出一个字体对话框。getFont()方法返回字体名字和布尔值。如果用户点击了OK，布尔值为True；否则为False。

    if ok:
        self.label.setFont(font)
如果我们点击了Ok按钮，标签字体会被改变。

Font dialogFigure: Font dialog

## 文件对话框
文件对话框是用于让用户选择文件或目录的对话框。可以选择文件的打开和保存。

    #!/usr/bin/python3
    # -*- coding: utf-8 -*-
    
    """
    ZetCode PyQt5 tutorial
    
    In this example, we select a file with a
    QFileDialog and display its contents
    in a QTextEdit.
    
    author: Jan Bodnar
    website: zetcode.com
    last edited: January 2015
    """
    
    import sys
    from PyQt5.QtWidgets import (QMainWindow, QTextEdit,
        QAction, QFileDialog, QApplication)
    from PyQt5.QtGui import QIcon
    
    
    class Example(QMainWindow):
        
        def __init__(self):
            super().__init__()
            
            self.initUI()
            
            
        def initUI(self):     
    
            self.textEdit = QTextEdit()
            self.setCentralWidget(self.textEdit)
            self.statusBar()
    
            openFile = QAction(QIcon('open.png'), 'Open', self)
            openFile.setShortcut('Ctrl+O')
            openFile.setStatusTip('Open new File')
            openFile.triggered.connect(self.showDialog)
    
            menubar = self.menuBar()
            fileMenu = menubar.addMenu('&File')
            fileMenu.addAction(openFile)      
            
            self.setGeometry(300, 300, 350, 300)
            self.setWindowTitle('File dialog')
            self.show()
            
            
        def showDialog(self):
    
            fname = QFileDialog.getOpenFileName(self, 'Open file', '/home')
    
            if fname[0]:
                f = open(fname[0], 'r')
    
                with f:
                    data = f.read()
                    self.textEdit.setText(data)       
            
    if __name__ == '__main__':
        
        app = QApplication(sys.argv)
        ex = Example()
        sys.exit(app.exec_())
示例中显示了一个菜单栏，中间设置了一个文本编辑框组件，和一个状态栏。点击菜单项会显示QtGui.QFileDialog（文件选择框）对话框，用于选择一个文件。文件的内容会被读取并在文本编辑框组件中显示。

    class Example(QMainWindow):
        
        def __init__(self):
            super().__init__()
            
            self.initUI()
示例基于QMainWindow组件，因为我们中心需要设置一个文本编辑框组件。

fname = QFileDialog.getOpenFileName(self, 'Open file', '/home')
弹出文件选择框。第一个字符串参数是getOpenFileName()方法的标题。第二个字符串参数指定了对话框的工作目录。默认的，文件过滤器设置成All files (*)。


    if fname[0]:
        f = open(fname[0], 'r')
    
        with f:
            data = f.read()
            self.textEdit.setText(data)
选中文件后，读出文件的内容，并设置成文本编辑框组件的显示文本、

File DialogFigure: File dialog

这部分的PyQt5教程中，我们学习了几种对话框的使用。

## PyQt5中的组件（widgets）
组件（widgets）是构建一个应用的基础模块。PyQt5有广泛的各式各样的组件，包含按钮，复选按钮，滑块条，和列表框。在这个部分的教程中，我们将学习几种有用的组件：

复选按钮（QCheckBox），切换按钮（ToggleButton），滑块条（QSlider），进度条（ProgressBar）和日历组件（QCalendarWidget）。

 
复选框（QCheckBox）
复选框组件有两种状态：选中和未选中。它是由一个选择框和一个标签组成的。一个应用中，复选框是典型的用来代表有效或无效状态的组件。

    #!/usr/bin/python3
    # -*- coding: utf-8 -*-
    
    """
    ZetCode PyQt5 tutorial
    
    In this example, a QCheckBox widget
    is used to toggle the title of a window.
    
    author: Jan Bodnar
    website: zetcode.com
    last edited: January 2015
    """
    
    import sys
    from PyQt5.QtWidgets import QWidget, QCheckBox, QApplication
    from PyQt5.QtCore import Qt
    
    
    class Example(QWidget):
        
        def __init__(self):
            super().__init__()
            
            self.initUI()
            
            
        def initUI(self):     
    
            cb = QCheckBox('Show title', self)
            cb.move(20, 20)
            cb.toggle()
            cb.stateChanged.connect(self.changeTitle)
            
            self.setGeometry(300, 300, 250, 150)
            self.setWindowTitle('QCheckBox')
            self.show()
            
            
        def changeTitle(self, state):
        
            if state == Qt.Checked:
                self.setWindowTitle('QCheckBox')
            else:
                self.setWindowTitle('')
                
            
    if __name__ == '__main__':
        
        app = QApplication(sys.argv)
        ex = Example()
        sys.exit(app.exec_())
在我们的例子中，我们创建了一个复选框，用来切换窗口标题。

1
cb = QCheckBox('Show title', self)
这是QCheckBox类的构造方法。

1
cb.toggle()
我们需要设置窗口标题，所以我们必须选中复选框。如果不选中复选框，默认情况下复选框不会被选中所以窗口标题也不会被设置。

1
cb.stateChanged.connect(self.changeTitle)
将我们自定义的changeTitle()槽方法和stateChanged信号连接。changeTitle()方法将用于切换窗口标题。

1
2
3
4
5
6
def changeTitle(self, state):
     
    if state == Qt.Checked:
        self.setWindowTitle('QCheckBox')
    else:
        self.setWindowTitle('')
复选框组件的状态会传入changeTitle()方法的state参数。如果复选框被选中，我们设置窗口标题。否则，我们把窗口标题设置成一个空字符串。

QCheckBoxFigure: QCheckBox

切换按钮
切换按钮是QPushButton的特殊模式。切换按钮有两种状态：按下和没有按下。我们可以通过点击它在两种状态之间切换。下面的列子展示了切换按钮合适出现的情景。

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
49
50
51
52
53
54
55
56
57
58
59
60
61
62
63
64
65
66
67
68
69
70
71
72
73
74
75
76
77
78
79
80
81
82
83
84
85
#!/usr/bin/python3
# -*- coding: utf-8 -*-
 
"""
ZetCode PyQt5 tutorial
 
In this example, we create three toggle buttons.
They will control the background colour of a
QFrame.
 
author: Jan Bodnar
website: zetcode.com
last edited: January 2015
"""
 
import sys
from PyQt5.QtWidgets import (QWidget, QPushButton,
    QFrame, QApplication)
from PyQt5.QtGui import QColor
 
 
class Example(QWidget):
     
    def __init__(self):
        super().__init__()
         
        self.initUI()
         
         
    def initUI(self):     
 
        self.col = QColor(0, 0, 0)      
 
        redb = QPushButton('Red', self)
        redb.setCheckable(True)
        redb.move(10, 10)
 
        redb.clicked[bool].connect(self.setColor)
 
        redb = QPushButton('Green', self)
        redb.setCheckable(True)
        redb.move(10, 60)
 
        redb.clicked[bool].connect(self.setColor)
 
        blueb = QPushButton('Blue', self)
        blueb.setCheckable(True)
        blueb.move(10, 110)
 
        blueb.clicked[bool].connect(self.setColor)
 
        self.square = QFrame(self)
        self.square.setGeometry(150, 20, 100, 100)
        self.square.setStyleSheet("QWidget { background-color: %s }" % 
            self.col.name())
         
        self.setGeometry(300, 300, 280, 170)
        self.setWindowTitle('Toggle button')
        self.show()
         
         
    def setColor(self, pressed):
         
        source = self.sender()
         
        if pressed:
            val = 255
        else: val = 0
                         
        if source.text() == "Red":
            self.col.setRed(val)               
        elif source.text() == "Green":
            self.col.setGreen(val)            
        else:
            self.col.setBlue(val)
             
        self.square.setStyleSheet("QFrame { background-color: %s }" %
            self.col.name()) 
        
        
if __name__ == '__main__':
     
    app = QApplication(sys.argv)
    ex = Example()
    sys.exit(app.exec_())
在我们的例子中，我们创建了三个切换按钮和一个QWidget组件。我们把QWidget组件的背景颜色设置为黑色。切换按钮将在红色，绿色和蓝色的RGB值部分进行切换。QWidget组件的背景颜色将取决于哪一个切换按钮被按下。

1
self.col = QColor(0, 0, 0)
这里是初始化，让RGB值为黑色。

1
2
3
redb = QPushButton('Red', self)
redb.setCheckable(True)
redb.move(10, 10)
要创建切换按钮，就要创建QPushButton，并且调用setCheckable()方法让它可被选中。

1
redb.clicked[bool].connect(self.setColor)
我们把clicked信号连接到我们定义的方法上。我们使用clicked信号来操作布尔值。

1
source = self.sender()
我们获得发生状态切换的按钮。

1
2
if source.text() == "Red":
    self.col.setRed(val)
在这种情况下，如果发生切换的是red按钮，我们更新RGB值中的红色部分的颜色值。

1
self.square.setStyleSheet("QWidget { background-color: %s }" %  self.col.name())
我们使用样式表来改变背景颜色。

 

Toggle button

Figure: Toggle button
滑块条(QSlider)
滑块条(QSlider)组件有一个简单的可调节手柄。这个手柄可以前后拖动。我们可以使用这个方式来选择具体的数值。有时使用滑块条比直接输入数字或使用数值选择框更自然，在我们下面的例子中，我们将显示一个滑块条和一个标签。标签将会显示一个图像。滑块条将控制标签。

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
49
50
51
52
53
54
55
56
57
58
59
60
61
#!/usr/bin/python3
# -*- coding: utf-8 -*-
 
"""
ZetCode PyQt5 tutorial
 
This example shows a QSlider widget.
 
author: Jan Bodnar
website: zetcode.com
last edited: January 2015
"""
 
import sys
from PyQt5.QtWidgets import (QWidget, QSlider,
    QLabel, QApplication)
from PyQt5.QtCore import Qt
from PyQt5.QtGui import QPixmap
 
 
class Example(QWidget):
     
    def __init__(self):
        super().__init__()
         
        self.initUI()
         
         
    def initUI(self):     
 
        sld = QSlider(Qt.Horizontal, self)
        sld.setFocusPolicy(Qt.NoFocus)
        sld.setGeometry(30, 40, 100, 30)
        sld.valueChanged[int].connect(self.changeValue)
         
        self.label = QLabel(self)
        self.label.setPixmap(QPixmap('mute.png'))
        self.label.setGeometry(160, 40, 80, 30)
         
        self.setGeometry(300, 300, 280, 170)
        self.setWindowTitle('QSlider')
        self.show()
         
         
    def changeValue(self, value):
 
        if value == 0:
            self.label.setPixmap(QPixmap('mute.png'))
        elif value > 0 and value <= 30:
            self.label.setPixmap(QPixmap('min.png'))
        elif value > 30 and value < 80:
            self.label.setPixmap(QPixmap('med.png'))
        else:
            self.label.setPixmap(QPixmap('max.png'))
             
 
if __name__ == '__main__':
 
    app = QApplication(sys.argv)
    ex = Example()
    sys.exit(app.exec_())
在我们的例子中，我们模拟了一个音量控制器。通过拖动滑块条的把手，我们可以改变标签的图像。

1
sld = QSlider(Qt.Horizontal, self)
这里我们创建了一个横向的滑块条。

1
2
self.label = QLabel(self)
self.label.setPixmap(QPixmap('mute.png'))
我们创建了一个标签组件，并且设置一个初始的无声图片。

1
sld.valueChanged[int].connect(self.changeValue)
我们把valueChanged 信号连接到我们自定义的 changeValue()方法上。

1
2
3
if value == 0:
    self.label.setPixmap(QPixmap('mute.png'))
...
这里实现了根据滑块条的值，我们设置不同的标签图片。在上面的代码中，如果滑块条的值等于零，我们为标签设置mute.png图片。

QSlider widget

Figure: QSlider widget
进度条（QProgressBar）
当我们处理耗时长的任务时，我们需要用到进度条组件。它通过动画的方式让我们了解任务正在处理中。在PyQt5中，进度条组件提供了横向和纵向的进度条选择。程序员可以设置进度条的最大值和最小值。进度条的默认值是0~99。

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
49
50
51
52
53
54
55
56
57
58
59
60
61
62
63
64
65
66
67
68
69
70
#!/usr/bin/python3
# -*- coding: utf-8 -*-
 
"""
ZetCode PyQt5 tutorial
 
This example shows a QProgressBar widget.
 
author: Jan Bodnar
website: zetcode.com
last edited: January 2015
"""
 
import sys
from PyQt5.QtWidgets import (QWidget, QProgressBar,
    QPushButton, QApplication)
from PyQt5.QtCore import QBasicTimer
 
 
class Example(QWidget):
     
    def __init__(self):
        super().__init__()
         
        self.initUI()
         
         
    def initUI(self):     
 
        self.pbar = QProgressBar(self)
        self.pbar.setGeometry(30, 40, 200, 25)
 
        self.btn = QPushButton('Start', self)
        self.btn.move(40, 80)
        self.btn.clicked.connect(self.doAction)
 
        self.timer = QBasicTimer()
        self.step = 0
         
        self.setGeometry(300, 300, 280, 170)
        self.setWindowTitle('QProgressBar')
        self.show()
         
         
    def timerEvent(self, e):
       
        if self.step >= 100:
            self.timer.stop()
            self.btn.setText('Finished')
            return
             
        self.step = self.step + 1
        self.pbar.setValue(self.step)
         
 
    def doAction(self):
       
        if self.timer.isActive():
            self.timer.stop()
            self.btn.setText('Start')
        else:
            self.timer.start(100, self)
            self.btn.setText('Stop')
             
         
if __name__ == '__main__':
     
    app = QApplication(sys.argv)
    ex = Example()
    sys.exit(app.exec_())
在我们的例子中有一个横向进度条和一个按钮。按钮控制滑块条的开始和停止。

1
self.pbar = QProgressBar(self)
这是滑块条类的构造方法。

1
self.timer = QtCore.QBasicTimer()
我们用定时器对象来激活进度条。

1
self.timer.start(100, self)
为了开启定时器事件，我们调用了start()方法。这个方法有两个参数：定时时间和接收定时器事件的对象。

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
def timerEvent(self, e):
   
    if self.step >= 100:
     
        self.timer.stop()
        self.btn.setText('Finished')
        return
         
    self.step = self.step + 1
    self.pbar.setValue(self.step)
每个QObject类和它的子类都有timerEvent()事件处理函数用于处理定时事件。为了对定时器事件作出反馈，我们重新实现了这个事件处理函数。

1
2
3
4
5
6
7
8
9
def doAction(self):
   
    if self.timer.isActive():
        self.timer.stop()
        self.btn.setText('Start')
         
    else:
        self.timer.start(100, self)
        self.btn.setText('Stop')
在doAction()方法中，我们开始和停止定时器。

QProgressBar

Figure: QProgressBar
日历组件（QCalendarWidget）
QCalendarWidget类提供了一个基于月的日历组件。它允许用户通过简单的直观的方式选择日期。

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
49
50
51
52
53
54
#!/usr/bin/python3
# -*- coding: utf-8 -*-
 
"""
ZetCode PyQt5 tutorial
 
This example shows a QCalendarWidget widget.
 
author: Jan Bodnar
website: zetcode.com
last edited: January 2015
"""
 
import sys
from PyQt5.QtWidgets import (QWidget, QCalendarWidget,
    QLabel, QApplication)
from PyQt5.QtCore import QDate
 
 
class Example(QWidget):
     
    def __init__(self):
        super().__init__()
         
        self.initUI()
         
         
    def initUI(self):     
 
        cal = QCalendarWidget(self)
        cal.setGridVisible(True)
        cal.move(20, 20)
        cal.clicked[QDate].connect(self.showDate)
         
        self.lbl = QLabel(self)
        date = cal.selectedDate()
        self.lbl.setText(date.toString())
        self.lbl.move(130, 260)
         
        self.setGeometry(300, 300, 350, 300)
        self.setWindowTitle('Calendar')
        self.show()
         
         
    def showDate(self, date):    
         
        self.lbl.setText(date.toString())
         
         
if __name__ == '__main__':
     
    app = QApplication(sys.argv)
    ex = Example()
    sys.exit(app.exec_())
以上的例子展示一个日历组件和标签组件。功能是日历中选择的日期会显示在标签组件中。

1
cal = QCalendarWidget(self)
创建QCalendarWidget类。

1
cal.clicked[QDate].connect(self.showDate)
如果我们在组件上选择了一个日期，clicked[QDate] 信号会被发射。我们把这个信号和自定义的showDate()方法连接。

1
2
3
def showDate(self, date):    
     
    self.lbl.setText(date.toString())
我们通过selectedDate()方法检索被选中的日期。然后我们把选中的日期对象转化成字符串显示在标签组件上。