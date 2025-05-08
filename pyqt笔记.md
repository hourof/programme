#   创建一个程序

```python
import sys
from PyQt5.QtWidgets import QApplication, QWidget, QPushButton, QVBoxLayout, QTextEdit
from PyQt5.QtCore import QTimer

class MyWindow(QWidget):
    def __init__(self):
        super().__init__()

        # 设置窗口标题
        self.setWindowTitle("PyQt 计数器示例")

        # 设置窗口大小
        self.setGeometry(100, 100, 400, 300)

        # 初始化计数器
        self.i = 0

        # 创建一个定时器
        self.timer = QTimer()
        self.timer.timeout.connect(self.update_counter)

        # 创建按钮
        self.start_button = QPushButton("开始", self)
        self.pause_button = QPushButton("暂停", self)

        # 连接按钮的点击事件到槽函数
        self.start_button.clicked.connect(self.start_counter)
        self.pause_button.clicked.connect(self.pause_counter)

        # 创建一个 QTextEdit 用于显示输出
        self.output_text = QTextEdit(self)
        self.output_text.setReadOnly(True)  # 设置为只读

        # 创建一个垂直布局
        layout = QVBoxLayout()

        # 将控件添加到布局中
        layout.addWidget(self.start_button)
        layout.addWidget(self.pause_button)
        layout.addWidget(self.output_text)

        # 设置窗口的布局
        self.setLayout(layout)

    def start_counter(self):
        # 启动定时器，每隔 1000 毫秒（1 秒）触发一次
        self.timer.start(1000)
        self.append_output("计数器已启动")

    def pause_counter(self):
        # 停止定时器
        self.timer.stop()
        self.append_output("计数器已暂停")

    def update_counter(self):
        # 更新计数器并显示
        self.i += 1
        self.append_output(f"计数器: {self.i}")

    def append_output(self, text):
        """将文本追加到 QTextEdit 中"""
        self.output_text.append(text)  # 追加文本并自动换行

if __name__ == "__main__":
    # 创建应用程序对象
    app = QApplication(sys.argv)

    # 创建窗口对象
    window = MyWindow()

    # 显示窗口
    window.show()

    # 进入应用程序的主循环
    sys.exit(app.exec_())
```

