# Windows 符号链接

在 Windows 操作系统中，符号链接（Symbolic Link，简称 Symlink）是一种特殊类型的文件，它充当对另一个文件或目录的引用。你可以将符号链接看作是一个快捷方式，它指向某个文件或目录的位置，使得你可以像访问常规文件一样访问目标文件或目录。

符号链接有两种类型：

1. **文件符号链接（File Symlink）**：
   - 这是指向一个文件的符号链接。当你访问符号链接时，实际上是访问链接所指向的文件。

2. **目录符号链接（Directory Symlink）**：
   - 这是指向一个目录的符号链接。当你访问符号链接时，实际上是访问链接所指向的目录。

## 如何创建符号链接

在 Windows 中，使用 `mklink` 命令来创建符号链接。

### 创建文件符号链接

```bash
mklink [Link] [Target]
```

- **Link**：符号链接的名称或路径。
- **Target**：目标文件的路径。

例如：

```bash
mklink C:\path\to\symlink.txt C:\path\to\original.txt
```

这将创建一个指向 `original.txt` 的符号链接 `symlink.txt`。

### 创建目录符号链接

```bash
mklink /D [Link] [Target]
```

- `/D` 参数表示创建的是目录符号链接。

例如：

```bash
mklink /D C:\path\to\symlink_folder C:\path\to\original_folder
```

这将创建一个指向 `original_folder` 目录的符号链接 `symlink_folder`。

## 符号链接的工作原理

符号链接是通过文件系统实现的，操作系统在你访问符号链接时会自动将其转换为指向的目标路径。这种机制使得符号链接成为一种非常方便的方式，用于创建虚拟文件系统结构或管理不同位置的文件和目录。

符号链接是一个独立的文件，它指向另一个文件或目录的路径。即使目标文件被删除，符号链接仍然存在，但会变成“死链接”。

可以像删除普通文件一样删除符号链接。直接删除符号链接文件或目录时，不会影响目标文件或目录。