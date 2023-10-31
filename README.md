import sys
from PyQt6.QtWidgets import QApplication, QWidget, QVBoxLayout, QPushButton

class MyApplication(QWidget):
    def __init__(self):
        super().__init__()
        self.initUI()

    def initUI(self):
        self.setWindowTitle('Button Program')

        self.button = QPushButton('Meni bosing')
        self.button.clicked.connect(self.buttonClicked)

        layout = QVBoxLayout()
        layout.addWidget(self.button)

        self.setLayout(layout)
        self.show()

    def buttonClicked(self):
        count = 0
        while True:
            user_input = input("Meni bosing")
            if user_input.lower() == "bos":
                count += 1
                print(f"Bos so'zini {count} marta kiritdingiz.")
            else:
                break

if __name__ == '__main__':
    app = QApplication(sys.argv)
    window = MyApplication()
    sys.exit(app.exec())
