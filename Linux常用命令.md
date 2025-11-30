# 1.查看当前目录

```c
pwd
```

# 2.查看目录下的所有文件

> ls

# 3.linux解压zip文件

在 Linux 中，你可以使用 `unzip` 命令来解压 `.zip` 文件。以下是一些常见的用法：

1. **解压到当前目录**：
   ```bash
   unzip filename.zip
   ```

2. **解压到指定目录**：
   ```bash
   unzip filename.zip -d /path/to/directory
   ```

3. **列出 `.zip` 文件的内容（不解压）**：
   
   ```bash
   unzip -l filename.zip
   ```
   
4. **解压带密码保护的 `.zip` 文件**：
   
   ```bash
   unzip -P yourpassword filename.zip
   ```

如果你的系统没有安装 `unzip`，可以使用以下命令安装：
- **Ubuntu/Debian**：
  
  ```bash
  sudo apt install unzip
  ```
- **CentOS/Fedora**：
  
  ```c
  

# 4.创建文件夹

在 Linux 下创建文件夹，你可以使用 `mkdir` 命令。以下是一些常见的用法：

1. **创建一个文件夹**：
   ```bash
   mkdir my_folder
   ```
   这样会在当前目录下创建 `my_folder` 文件夹。

2. **创建多个文件夹**：
   ```bash
   mkdir folder1 folder2 folder3
   ```
   这样会同时创建 `folder1`、`folder2` 和 `folder3`。

3. **创建多级目录（如果上级目录不存在，会自动创建）**：
   ```bash
   mkdir -p parent/child/grandchild
   ```
   `-p` 选项允许创建嵌套目录，即如果 `parent` 目录还不存在，它也会自动创建。

4. **检查文件夹是否创建成功**：
   ```bash
   ls -l
   ```
   或者：
   ```bash
   ls -d my_folder
   
   
   ```

