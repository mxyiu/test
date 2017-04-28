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

**注意：**

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
   //添加所有改动
   git add -A
   //添加新建的文件和修改过的文件，但是不包括删除掉的文件
   git add *
   git add .
   //添加修改过的文件和删除掉的文件，但是不包括新建的文件
   git add -u
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

如果想要查看当前状态，则可以通过以下命令来查看，它会告诉你相应的状态。

**注意：** 标红表示文件未add到暂存区，标绿表示文件已经add到了暂存区。

```git
git status
```

- 当文件修改，没有add到暂存区的时候，可以用以下命令撤销修改，即变回上次提交时的样子。

  ```git
  git checkout -- <file>
  ```

- 当文件修改，且已经add到暂存区后，可以用以下命令修改。

  ```git
  //重置暂存区，文件保持最后的保存状态
  git reset HEAD <file>
  //撤销修改
  git checkout -- <file>
  ```

如果你不记得修改过什么了，通过一下命令可以查看不同之处，可以知道做了什么修改。

*注意：* 只有在没有添加到暂存区和仓库的时候，这个命令才有效。

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

