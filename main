import sys
import random
from PyQt5.QtWidgets import QApplication, QMainWindow
from PyQt5.QtGui import QPainter, QColor
from ultra_code import Ui_MainWindow
from random import randint


class Circles(QMainWindow, Ui_MainWindow):
    def __init__(self):
        super().__init__()
        self.setupUi(self)
        self.drawCircle = False
        self.draw_button.move(self.height() // 2, self.width() // 2)
        self.draw_button.clicked.connect(self.let_draw)
        self.HTML_LIST = []

    def let_draw(self):
        self.drawCircle = True
        self.update()

    def draw_crc(self, qp):
        rand = (randint(0, 255), randint(0, 255), randint(0, 255))
        ox = random.randint(100, 400)
        oy = random.randint(100, 400)
        radius = random.randint(10, 90)
        self.HTML_LIST.append([ox, oy, radius, radius, rand])
        for i in self.HTML_LIST:
            qp.setBrush(QColor(*i[-1]))
            qp.drawEllipse(*i[:-1])

    def paintEvent(self, event):
        if self.drawCircle is True:
            qp = QPainter()
            qp.begin(self)
            self.draw_crc(qp)
            qp.end()
            self.drawCircle = False


if __name__ == '__main__':
    app = QApplication(sys.argv)
    crc = Circles()
    crc.show()
    sys.exit(app.exec())
