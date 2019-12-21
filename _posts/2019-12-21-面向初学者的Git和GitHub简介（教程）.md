# 面向初学者的Git和GitHub简介（教程）



##  步骤3: 将文件添加到暂存环境

使用**git add**命令将文件添加到暂存环境。

如果重新运行 命令，你将看到git已将该文件添加到暂存环境（请注意“要提交的更改”行）。

 `mnelson:myproject mnelson$ git status On branch master Initial commit Changes to be committed:  (use "git rm --cached ..." to unstage) 	new file:   mnelson.txt`[view raw](https://gist.github.com/cubeton/28f7bea3b232f67e031c/raw/875157cd78d75c23f3f0e29bf0c97989e3d52937/addtostaging.md)[addtostaging.md](https://gist.github.com/cubeton/28f7bea3b232f67e031c#file-addtostaging-md) hosted with ❤ by [GitHub](https://github.com)



```
mnelson:myproject mnelson$ git status
On branch master

Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

	new file:   mnelson.txt
```

[view raw](https://gist.github.com/cubeton/28f7bea3b232f67e031c/raw/875157cd78d75c23f3f0e29bf0c97989e3d52937/addtostaging.md)[addtostaging.md](https://gist.github.com/cubeton/28f7bea3b232f67e031c#file-addtostaging-md) hosted with ❤ by [GitHub](https://github.com/)



 再次重申，该文件 **尚未** 添加到提交，但它即将被提交。

 

## 步骤4：创建提交

是时候创建你的第一个提交了！

运行命令 `git commit -m "Your message about the commit"`



```
mnelson:myproject mnelson$ git commit -m "This is my first commit!"
[master (root-commit) b345d9a] This is my first commit!
 1 file changed, 1 insertion(+)
 create mode 100644 mnelson.txt
```

[view raw](https://gist.github.com/cubeton/1068d965d147b4039e4d/raw/5c3262c3f6e3c28328ba57ea33c512dbab149fcf/commit.md)[commit.md](https://gist.github.com/cubeton/1068d965d147b4039e4d#file-commit-md) hosted with ❤ by [GitHub](https://github.com)



```
mnelson:myproject mnelson$ git commit -m "This is my first commit!"
[master (root-commit) b345d9a] This is my first commit!
 1 file changed, 1 insertion(+)
 create mode 100644 mnelson.txt
```

[view raw](https://gist.github.com/cubeton/1068d965d147b4039e4d/raw/5c3262c3f6e3c28328ba57ea33c512dbab149fcf/commit.md)[commit.md](https://gist.github.com/cubeton/1068d965d147b4039e4d#file-commit-md) hosted with ❤ by [GitHub](https://github.com/)



提交结束时的消息应该与提交包含的内容相关 - 也许它是一个新功能，也许它是一个错误修复，也许它只是修复一个错字。不要像 “asdfadsf”或“foobar”这样的消息。这让其他人看到你的消息让人伤心。非常，非常，悲伤。

 

## 步骤5：创建一个新分支

现在你已经做了一个新的提交，让我们尝试 一些更高级的东西。

假设你想创建一个新功能，但担心在开发 该功能时对主项目进行更改。 这就是 **[git分支](https://git-scm.com/book/en/v1/Git-Branching-What-a-Branch-Is)** 的作用。 

分支允许你在项目的“状态”之间来回移动。例如，如果要向网站添加新页面，可以仅为该页面创建新分支， 而不影响 项目的主要部分。 完成页面后，你可以 [**合并**](http://git-scm.com/docs/git-merge) 更改从你的分支到主分支中。 当你创建一个新的分支时， Git 会跟踪这个分支的提交，所以它知道所有文件背后的历史。 

假设你在主分支机构并且想要创建一个新分支来开发你的网页。 下面是你要做的：运行 **[`git checkout -b `](http://git-scm.com/docs/git-checkout)**.这个命令将自动创建一个新的分支，然后对其“检查出来”，这意味着git会将你移动到主分支之外的那个分支。

运行上述命令后， 你可以使用该 **[`git branch`](http://git-scm.com/docs/git-branch)** 命令确认你的分支已创建：



```
mnelson:myproject mnelson$ git branch
  master
* my-new-branch
```

[view raw](https://gist.github.com/cubeton/fa25a25f322a2cd5f405/raw/81033788d288adeffe260bd724ab2699b29e3e35/gitbranch.md)[gitbranch.md](https://gist.github.com/cubeton/fa25a25f322a2cd5f405#file-gitbranch-md) hosted with ❤ by [GitHub](https://github.com)



```
mnelson:myproject mnelson$ git branch
  master
* my-new-branch
```

[view raw](https://gist.github.com/cubeton/fa25a25f322a2cd5f405/raw/81033788d288adeffe260bd724ab2699b29e3e35/gitbranch.md)[gitbranch.md](https://gist.github.com/cubeton/fa25a25f322a2cd5f405#file-gitbranch-md) hosted with ❤ by [GitHub](https://github.com/)



旁边带星号的分支名称指示在给定时间指向哪个分支。 

现在，如果你切换回主分支并进行更多提交，你的新分支不会看到任何这些更改，直到你将这些更改 [**合并**](http://git-scm.com/docs/git-merge) 到新分支当中。