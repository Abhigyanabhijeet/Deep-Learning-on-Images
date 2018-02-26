Step 1) Design in Qt creator 


Step 2) Convert *.ui to *.py using
    
    pyuic -x input.ui -o output.py
    
step 3) Make a new file main.py and input the following code :
    import sys
    from PyQt5 import QtCore, QtGui, uic,QtWidgets
 
    import mainwindow
 
    class MyApp(QtWidgets.QMainWindow, mainwindow.Ui_MainWindow):
        def __init__(self,parent=None):
            super(MyApp, self).__init__(parent)
            self.setupUi(self)


    if __name__ == '__main__':
        app = QtWidgets.QApplication.instance()
        if app is None:
            app = QtWidgets.QApplication(sys.argv)
        else:
            print('QApplication instance already exists: %s' % str(app))
        window = MyApp()
        window.show()
        app.exec_()
