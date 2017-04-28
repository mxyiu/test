## 关于Git的使用

### 什么是Git？

Git是一个分布式版本管理系统。

相关下载：

- [Windows平台](https://git-for-windows.github.io/)
- [Mac平台](https://book.git-scm.com/download/mac)
- [Linux平台](https://book.git-scm.com/download/linux)

下载安装完毕后需要配置你的身份。

```git
git config --global user.name "your name"
git config --global user.email "your email address"
```

**注意**：

- 当使用了`--global`这个参数，你的电脑上所有的repository都会使用这个配置，支持对某个repository指定不同的user name和user email。
- 如果想验证是否配置成功，则把name和email去掉在输入一次命令，看显示的用户名和邮箱是否正确。

### Git如何操作？

首先可以选择在你的项目目录内创建repo，会在该目录下生成一个名为`.git`的隐藏文件。

```git
git init
```

基本的工作流程如下：

1. 在工作目录`working directory`中修改文件。

2. 把文件先添加到`staging area`即暂存区。

   ```git
   git add <filename>
   ```

   也可以一次全部添加。

   ```git
   git add .
   ```

3. 提交更新到repo。

   ```git
   git commit -m "description"
   ```

即创建了repo之后，需要把文件添加进repo的暂存区，然后提交到本地仓库。

若你想克隆远程服务器现有的项目，则需要使用到`git clone`命令。

例如：

```git
git clone https://github.com/example/repo
```

查看当前状态。

```git
git status
```

查看不同。

```git
git diff
```

查看日志。

```git
git log
```

查看命令历史

```git
git reflog
```

