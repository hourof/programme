# 1.读取文本文件内容

在 Python 中，你可以使用 `open()` 函数来读取 `0.txt` 文件的内容。以下是几种常见的读取方法：

### **1. 读取整个文件内容**
```python
with open("0.txt", "r", encoding="utf-8") as file:
    content = file.read()
    print(content)
```
这个方法会一次性读取整个文件，并打印内容。如果 `0.txt` 包含中文或特殊字符，最好指定 `encoding="utf-8"` 来防止编码错误。

---

### **2. 按行读取文件**
如果文件内容很大，你可以逐行读取：
```python
with open("0.txt", "r", encoding="utf-8") as file:
    for line in file:
        print(line.strip())  # 使用 `strip()` 去除行末的换行符
```

---

### **3. 读取为列表**
如果想将所有行存储在列表中：
```python
with open("0.txt", "r", encoding="utf-8") as file:
    lines = file.readlines()  # 返回一个列表，每行作为列表项
    print(lines)
```

---

### **4. 检查文件是否存在**
如果不确定 `0.txt` 是否存在，可以先检查：
```python
import os

if os.path.exists("0.txt"):
    with open("0.txt", "r", encoding="utf-8") as file:
        content = file.read()
        print(content)
else:
    print("文件不存在！")
```

这样就可以安全地读取 `0.txt` 了！如果你需要按格式解析数据，或者做进一步处理，比如提取特定内容，我可以帮你优化代码！🚀

# 2.将字符串解析为列表,每个空格是分割地方

```python
data = "Hello word"
data_list = data.split()
print(data_list)

output_test:
    ["Hello","world"]
```



# 3.range方法

```python
range(0, len(data_list), 5):

#这是一个 range() 生成器，从 0 开始，步长为 5，直到 len(data_list) 结束
#举例,有这么一段代码
for i in range(0,30,5):
    print(i)

#输出结果
0
5
10
15
20
25
```

# 4.列表切片 list[start_list:end_list]

```python
my_list =[]
for i in range(30):
    my_list.append(i)

print(my_list)
#进行列表切片,生成一个新的列表
new_list = []
#这里的0代表列表起始索引,10是结束索引
#把起始索引,和结束索引的值生成一个新的列表
new_list = my_list[0:10]
print(new_list)
```

# 5. Python strip()方法

`strip()` 是 Python **字符串方法**，用于 **删除字符串两端的空白字符**（包括空格、换行符 `\n`、制表符 `\t` 等）。

### 1. **基本用法**
```python
text = "  Hello, World!  "
clean_text = text.strip()
print(clean_text)  # 输出: "Hello, World!"
```
这里，`strip()` **去除了开头和结尾的空格**。

### **去除特定字符**
你可以指定要去除的字符：
```python
text = "xxHello, Pythonxx"
clean_text = text.strip("x")  # 去除两端的 'x'
print(clean_text)  # 输出: "Hello, Python"
```
> `strip("x")` 只会删除字符串 **两端** 的 `'x'`，中间的 `'x'` 不受影响。

### **`lstrip()` 和 `rstrip()`**
- `lstrip()` 只去除 **左侧**（开头）的字符：
  ```python
  text = "   Hello"
  print(text.lstrip())  # 输出: "Hello"
  ```
- `rstrip()` 只去除 **右侧**（结尾）的字符：
  ```python
  text = "Hello   "
  print(text.rstrip())  # 输出: "Hello"
  ```

### **处理换行符 `\n`**
```python
text = "Python is great!\n"
print(text.strip())  # 输出: "Python is great!"
```
这样 `\n` 也会被去掉。`strip()` 是 Python **字符串方法**，用于 **删除字符串两端的空白字符**（包括空格、换行符 `\n`、制表符 `\t` 等）。

### **总结**
- `strip()` **去除两端** 空白字符或指定字符。
- `lstrip()` **去除左侧**（开头）字符。
- `rstrip()` **去除右侧**（结尾）字符。

这个方法常用于 **数据清理**，比如去掉用户输入中的空格、去除文件读取时的换行符等。

# 6. python split方法

> `split()` 是 Python **字符串方法**，用于 **按照指定的分隔符拆分字符串**，并返回一个 **列表**。

---

### **基本用法**
```python
text = "apple banana cherry"
words = text.split()  # 默认按空格拆分
print(words)
```
**输出：**
```
['apple', 'banana', 'cherry']
```
`split()` 默认 **按空格** 分割字符串，并去掉多余空格。

---

### **使用自定义分隔符**
你可以指定任何分隔符：
```python
text = "apple,banana,cherry"
words = text.split(",")  # 以逗号 `,` 作为分隔符
print(words)
```
**输出：**
```
['apple', 'banana', 'cherry']
```

---

### **限制拆分次数**
你可以使用 `maxsplit` 参数 **限制拆分的次数**：
```python
text = "one|two|three|four|five"
parts = text.split("|", 2)  # 只拆分两次
print(parts)
```
**输出：**
```
['one', 'two', 'three|four|five']
```
这里只拆分了 **两次**，剩下的部分不再拆分。

---

### **拆分换行符**
```python
text = "Hello\nPython\nWorld"
lines = text.split("\n")  # 按换行符拆分
print(lines)
```
**输出：**
```
['Hello', 'Python', 'World']
```

---

### **与 `join()` 搭配**
如果你用 `split()` 拆分字符串后，可以用 `join()` 重新组合：
```python
text = "apple,banana,cherry"
words = text.split(",")  # 拆分
new_text = "-".join(words)  # 用 `-` 重新连接
print(new_text)
```
**输出：**
```
apple-banana-cherry
```
`join()` 可以把列表拼接成字符串，和 `split()` 是 **互补关系**。

---

### **总结**
- `split()` **默认按空格分割**，返回列表。
- 你可以 **指定分隔符**，如 `split(",")` 按逗号分割。
- `split(sep, maxsplit)` **限制拆分次数**。
- `join()` **可以将列表重新拼接成字符串**。

# 7.python map高阶函数

`map()` 是 Python 的 **高阶函数**，用于 **对可迭代对象的每个元素应用一个函数**，并返回一个新的迭代器。

### **基本用法**
```python
numbers = [1, 2, 3, 4, 5]
squared = map(lambda x: x**2, numbers)  # 对列表中每个元素求平方
print(list(squared))  # 转换为列表输出
```
**输出：**
```
[1, 4, 9, 16, 25]
```

### **如何使用 `map()`**
- `map(function, iterable)`：
  - **`function`** 是应用到每个元素的函数。
  - **`iterable`** 是一个可迭代对象（如列表、元组等）。
  - 返回一个 **map 对象**（是个迭代器）。
  - 你通常需要用 `list()` 或 `tuple()` 转换成可见的数据。

---

### **多个可迭代对象**
你可以传入 **多个列表**：
```python
a = [1, 2, 3]
b = [4, 5, 6]
summed = map(lambda x, y: x + y, a, b)  # 对应元素相加
print(list(summed))
```
**输出：**
```
[5, 7, 9]
```

---

### **使用 `map()` 转换字符串**
```python
words = ["hello", "world", "python"]
upper_words = map(str.upper, words)  # 调用 `upper()` 转换大写
print(list(upper_words))
```
**输出：**
```
['HELLO', 'WORLD', 'PYTHON']
```

---

### **替代方案：列表推导式**
有时 **`map()` 可以用列表推导式替代**：
```python
numbers = [1, 2, 3, 4, 5]

# 使用 map()：
squared_map = list(map(lambda x: x**2, numbers))

# 使用列表推导式：
squared_list = [x**2 for x in numbers]

print(squared_map)  # [1, 4, 9, 16, 25]
print(squared_list) # [1, 4, 9, 16, 25]
```
两者功能相同，但 **列表推导式更直观**。

---

### **总结**
- `map()` 可以对 **可迭代对象的每个元素** 进行 **函数处理**。
- 适用于 **多个可迭代对象**（如 `map(lambda x, y: x + y, list1, list2)`）。
- 结果是一个 **迭代器**，通常需要用 `list()` 转换。
- **列表推导式** 是 `map()` 的另一种替代方案，通常更易读。

如果你有具体需求，我可以帮你优化代码！ 🚀😃

# 8. os模块

## 1.查看是否有文件名字,如果路径下没有就创建文件

```python
os.makedirs("filename",exist_ok= True)

```

## 2.文件拼接

```
filename = os.path.join("path1", "path2")
```



# 9.python字符串

### **.replace(old, new)方法**
- `.replace(old, new)` 会将字符串中的 `old` 替换为 `new`，但不会修改原字符串，而是返回一个新的字符串。
- 该方法只会替换匹配的部分，不会检查文件扩展名是否正确，因此如果文件名本身包含 `"jpg"`，它也会被替换：
    ```python
    filename = "myjpgfile.jpg"
    print(filename.replace("jpg", "txt"))  # 输出: mytxtfile.txt
    ```
    如果你想只替换扩展名，可以考虑 `os.path.splitext()`：
    ```python
    import os
    filename = "image.jpg"
    name, ext = os.path.splitext(filename)
    new_filename = name + ".txt"
    print(new_filename)  # 输出: image.txt
    ```

如果你要批量处理一系列文件名（比如 `images_list`），你可以这样写：
```python
images_list = ["1.jpg", "2.jpg", "3.jpg", "4.jpg", "5.jpg", "6.jpg", "7.jpg"]
txt_list = [img.replace("jpg", "txt") for img in images_list]  # 生成对应的 txt 文件名
print(txt_list)  # 输出: ['1.txt', '2.txt', '3.txt', '4.txt', '5.txt', '6.txt', '7.txt']
```

这样，你就能轻松转换文件扩展名。希望这个方法对你有帮助！🚀
