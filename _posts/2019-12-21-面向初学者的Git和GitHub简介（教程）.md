# 面向初学者的Git和GitHub简介（教程）



 八月, 我们在HubSpot举办了一场 [女性计算机代码工作者的见面会](http://www.meetup.com/Women-Who-Code-Boston/events/224072838/) ，为初学者开展了一个关于使用 git和Github的研讨会。我首先通过 [幻灯片](https://www.slideshare.net/HubSpot/git-101-git-and-github-for-beginners)介绍了git的基础知识和背景知识，之后将大家分为小组来操作我创建的教程，用来模拟 大型项目协作工作。项目之后，我们得到了大家的反馈，这次教程非常有帮助，并且也是个可实施的教程。所以 如果你也是git新用户, 请按照下面的步骤轻松更改代码，打开请求 (PR), 将代码合并到 主分支。任何重要的git和GitHub术语都用粗体显示，并附有官方git参考资料链接。  



### 开始： 安装git并创建GitHub账户 

你需要做的前两件事是安装git并且创建GitHub的免费账户

按照[此处](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) 说明安装 git（如果你未安装） 请注意， 这些教程只能在命令行上使用。虽然有一些不错的git GUIS（图形用户界面）,我认为先使用git特定的命令来学习git会更容易，然后在熟悉了该命令之后再尝试使用git GUI。 

一旦你对那些命令熟悉了，就可以尝试 [这里的](https://github.com/join).  git GUIS(账户的公共仓库是免费的。但是私人仓库是付费的)

 

### 步骤1： 创建本地git存储库 

使用git在本地机器上创建新项目时，首先要创建一个新 **[存储库](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository)** (或者通常是'**repo**'). 

要使用git，我们将使用终端。如果您对终端和基本命令没有太多经验，请查看 [本教程](http://mac.appstorm.net/how-to/utilities-how-to/how-to-use-terminal-the-basics/) (尤其是“导航文件系统”和“移动”部分).

首先，打开终端并使用`cd` (更改目录) 命令移动到要将项目放置在本地计算机上的位置.例如，如果桌面上有“项目”文件夹，则可以执行以下操作：



```
mnelson:Desktop mnelson$ cd ~/Desktop
mnelson:Desktop mnelson$ mkdir myproject
mnelson:Desktop mnelson$ cd myproject/
```

[view raw](https://gist.github.com/cubeton/67a84eb876984f0b5785/raw/d4560016d742865c1fd68d97fcff1feb557d5e19/terminalcd.md)[terminalcd.md](https://gist.github.com/cubeton/67a84eb876984f0b5785#file-terminalcd-md) hosted with ❤ by [GitHub](https://github.com)



```
mnelson:Desktop mnelson$ cd ~/Desktop
mnelson:Desktop mnelson$ mkdir myproject
mnelson:Desktop mnelson$ cd myproject/
```

[view raw](https://gist.github.com/cubeton/67a84eb876984f0b5785/raw/d4560016d742865c1fd68d97fcff1feb557d5e19/terminalcd.md)[terminalcd.md](https://gist.github.com/cubeton/67a84eb876984f0b5785#file-terminalcd-md) hosted with ❤ by [GitHub](https://github.com/)



 

要在文件夹的根目录中初始化git存储库，请运行 **[git init](http://git-scm.com/docs/git-init)** 命令: 

```
mnelson:myproject mnelson$ git init
Initialized empty Git repository in /Users/mnelson/Desktop/myproject/.git/
```

[view raw](https://gist.github.com/cubeton/89793ba1bc947f64658e/raw/f3dba1dd72fda5eeb98b761338aedfc310d29d54/gitinit.md)[gitinit.md](https://gist.github.com/cubeton/89793ba1bc947f64658e#file-gitinit-md) hosted with ❤ by [GitHub](https://github.com)

```
mnelson:myproject mnelson$ git init
Initialized empty Git repository in /Users/mnelson/Desktop/myproject/.git/
```

[view raw](https://gist.github.com/cubeton/89793ba1bc947f64658e/raw/f3dba1dd72fda5eeb98b761338aedfc310d29d54/gitinit.md)[gitinit.md](https://gist.github.com/cubeton/89793ba1bc947f64658e#file-gitinit-md) hosted with ❤ by [GitHub](https://github.com/)

###  

### 步骤2: 向repo添加新文件

继续使用你喜欢的任何文本编辑器或运行 [touch](http://linux.die.net/man/1/touch) 命令将新文件添加到项目中.

一旦你在包含git repo的文件夹中添加或修改了文件，git就会发现在repo中已经进行了更改。但是，git不会正式跟踪文件（也就是说，将其置于提交中-我们将在下面详细讨论提交），除非你明确告诉它。



```
mnelson:myproject mnelson$ touch mnelson.txt
mnelson:myproject mnelson$ ls
mnelson.txt
```

[view raw](https://gist.github.com/cubeton/2d8f224bede4c2dde86b/raw/b865e27cc4715b3a3a4a5839e77ab232ff1b31f9/addfile.md)[addfile.md](https://gist.github.com/cubeton/2d8f224bede4c2dde86b#file-addfile-md) hosted with ❤ by [GitHub](https://github.com)



```
mnelson:myproject mnelson$ touch mnelson.txt
mnelson:myproject mnelson$ ls
mnelson.txt
```

[view raw](https://gist.github.com/cubeton/2d8f224bede4c2dde86b/raw/b865e27cc4715b3a3a4a5839e77ab232ff1b31f9/addfile.md)[addfile.md](https://gist.github.com/cubeton/2d8f224bede4c2dde86b#file-addfile-md) hosted with ❤ by [GitHub](https://github.com/)



 

创建新文件后，你可以使用该 [**`git status`**](http://git-scm.com/docs/git-status) 命令查看git知道哪些文件存在。



```
mnelson:myproject mnelson$ git status
On branch master

Initial commit

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	mnelson.txt

nothing added to commit but untracked files present (use "git add" to track)
```

[view raw](https://gist.github.com/cubeton/02e849bbffcbea1e9a61/raw/71c93139666a8a4e06795f53c9aec5db95e6019a/gitstatus.md)[gitstatus.md](https://gist.github.com/cubeton/02e849bbffcbea1e9a61#file-gitstatus-md) hosted with ❤ by [GitHub](https://github.com)



```
mnelson:myproject mnelson$ git status
On branch master

Initial commit

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	mnelson.txt

nothing added to commit but untracked files present (use "git add" to track)
```

[view raw](https://gist.github.com/cubeton/02e849bbffcbea1e9a61/raw/71c93139666a8a4e06795f53c9aec5db95e6019a/gitstatus.md)[gitstatus.md](https://gist.github.com/cubeton/02e849bbffcbea1e9a61#file-gitstatus-md) hosted with ❤ by [GitHub](https://github.com/)



这基本上是说, "嘿, 我们注意到你创建了一个名为mnelson.txt的新文件，但除非你使用'`git add' `命令，否则我们不会对它做任何事情。"



### 提示：准备环境、提交和用户

你第一次学校git时最困惑的部分之一是准备环境的概念以及它与提交的关系。

**[提交](http://git-scm.com/docs/git-commit)** 是自上次提交以来更改了哪些文件的记录。实际上，您对repo进行了更改（例如，添加文件或修改文件），然后告诉git将这些文件放入提交。

提交构成了项目的本质，并允许您在任何时候返回到项目的状态。

那么，你如何告诉git将哪些文件放入提交中？ 这就是 [**准备环境** 或 **索引**](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics)的位置. 如步骤2所示, 当你对repo进行更改时，git会注意到文件已更改但不会对其执行任何操作（例如在提交中添加它）。

要将文件添加到提交，首先需要将其添加到准备环境。为此，你可以使用 **[git add](http://git-scm.com/docs/git-add) ** 命令 (请参阅下面的步骤3).

一旦你使用git add命令将你想要的所有文件添加到准备环境，你就可以告诉git使用 [**git commit** ](http://git-scm.com/docs/git-commit)命令将它们打包到一个提交中. 

注意：暂存环境（也称为“暂存”）是新的首选术语，但你也可以将其称为“索引”.





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



### 步骤6:在 GitHub上创建新的仓库

如果你只想在本地跟踪代码，则无需使用GitHub。 但是，如果你想与团队合作，则可以使用GitHub协同修改项目代码。

 

如果要在GitHub上创建新的仓库，请登录并转到GitHub主页。 你会看到一个绿色的“+ New repository ”按钮：

![[](https://cdn.jsdelivr.net/gh/reloaded7/zhangzhizhi@2.7/git1.webp.jpg)](https://cdn.jsdelivr.net/gh/reloaded7/zhangzhizhi@2.7/git1.webp.jpg)

 单击按钮后，GitHub将要求你命名仓库并提供简短描述： 

![](https://cdn.jsdelivr.net/gh/reloaded7/zhangzhizhi@2.7/git2.webp.jpg)

填写完信息后，请按“Create repository”按钮以创建新的仓库。

GitHub会询问你是否要从头开始创建新的仓库，或者是否要添加在本地创建的仓库。 在这种情况下，由于我们已经在本地创建了新的仓库，因此我们希望将其推送到GitHub上，因此请遵循 **“....或从命令行推送现有仓库”** 部分： 

 

```
mnelson:myproject mnelson$ git remote add origin https://github.com/cubeton/mynewrepository.git
mnelson:myproject mnelson$ git push -u origin master
Counting objects: 3, done.
Writing objects: 100% (3/3), 263 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/cubeton/mynewrepository.git
 * [new branch]      master -> master
Branch master set up to track remote branch master from origin.
```

[view raw](https://gist.github.com/cubeton/3a2616c44e35ca68a6b0/raw/41e5758cfdbd7db8a1659c1adaba9346680097f9/addgithub.md)[addgithub.md](https://gist.github.com/cubeton/3a2616c44e35ca68a6b0#file-addgithub-md) hosted with ❤ by [GitHub](https://github.com)](https://github.com/)

```
mnelson:myproject mnelson$ git remote add origin https://github.com/cubeton/mynewrepository.git
mnelson:myproject mnelson$ git push -u origin master
Counting objects: 3, done.
Writing objects: 100% (3/3), 263 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/cubeton/mynewrepository.git
 * [new branch]      master -> master
Branch master set up to track remote branch master from origin.
```

[view raw](https://gist.github.com/cubeton/3a2616c44e35ca68a6b0/raw/41e5758cfdbd7db8a1659c1adaba9346680097f9/addgithub.md)[addgithub.md](https://gist.github.com/cubeton/3a2616c44e35ca68a6b0#file-addgithub-md) hosted with ❤ by [GitHub](https://github.com/)

（由于你的GitHub用户名和仓库名称不同，因此你需要将第一个命令行中的URL更改为本节中GitHub列出的内容） 

 

### 步骤7：将分支推送到GitHub

现在，我们将分支中的提交**推送**到新的GitHub仓库。这使其他人可以看到你所做的更改。 如果它们是由仓库拥有者同意的，则可以将其更改合并到主分支中。

要将更改推送到GitHub上的新分支，你需要运行 `**[git push](http://git-scm.com/docs/git-push)origin yourbranchname**. ```GitHub将在远程仓库上自动为你创建分支： 

```
mnelson:myproject mnelson$ git push origin my-new-branch
Counting objects: 3, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 313 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/cubeton/mynewrepository.git
 * [new branch]      my-new-branch -> my-new-branch
```

[view raw](https://gist.github.com/cubeton/bf8274609c344b6d0e70/raw/4764e740cac9a48eefad341d9e34ceb09f89b73f/addnewbranchgithub.md)[addnewbranchgithub.md](https://gist.github.com/cubeton/bf8274609c344b6d0e70#file-addnewbranchgithub-md) hosted with ❤ by [GitHub](https://github.com)

```
mnelson:myproject mnelson$ git push origin my-new-branch
Counting objects: 3, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 313 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/cubeton/mynewrepository.git
 * [new branch]      my-new-branch -> my-new-branch
```

[view raw](https://gist.github.com/cubeton/bf8274609c344b6d0e70/raw/4764e740cac9a48eefad341d9e34ceb09f89b73f/addnewbranchgithub.md)[addnewbranchgithub.md](https://gist.github.com/cubeton/bf8274609c344b6d0e70#file-addnewbranchgithub-md) hosted with ❤ by [GitHub](https://github.com/)

你可能想知道上面命令中“origin”一词的含义。当你将远程仓库克隆到本地计算机时，git为你创建了一个**别名**。在几乎所有情况下，此别名都称为[**origin**](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes) 。它实质上是远程仓库URL的简写。 因此，要将更改推送到远程仓库，可以使用以下命令： **`git push git@github.com:git/git.git yourbranchname`** 或者**`git push origin yourbranchname`**

（如果这是你第一次在本地使用GitHub，则可能会提示你使用GitHub用户名和密码登录。）

如果刷新GitHub页面，你会看到注释，说你的名字的分支刚刚被推送到仓库中。 你也可以单击”branches“链接以查看此处列出的分支。

![](https://cdn.jsdelivr.net/gh/reloaded7/zhangzhizhi@2.7/git3.webp.jpg)

 现在，单击上方屏幕截屏中的绿色按钮。 我们将提出**发送请求**！ 

### 步骤8：创建发送请求（PR）

发送请求（或PR）是一种提醒仓库拥有者要更改其代码的方式。 它允许他们在将更改放在主分支上之前检查代码并确保它看起来很好。

这是PR页面在你提交之前的样子：

![](https://cdn.jsdelivr.net/gh/reloaded7/zhangzhizhi@2.7/git4.webp.jpg)

 这就是你提交PR请求后的样子 ： 

![](https://cdn.jsdelivr.net/gh/reloaded7/zhangzhizhi@2.7/git5.webp.jpg)

你可能会在底部看到一个绿色的大按钮，上面显示“Merge pull request”。 单击这意味着你将你的更改合并到主分支中。

请注意，此按钮并非总是绿色。 在某些情况下，它会是灰色的，这意味着你面临 **合并冲突**。这是当一个文件中的更改与另一个文件中的更改冲突时，git无法确定要使用的版本。你必须手动进入并告诉git使用哪个版本。

有时你将成为共同所有者或回购的唯一所有者，在这种情况下，你可能不需要创建PR来合并你的更改。但是，创建一个分支仍然是一个好主意，这样你可以保留更新的更完整历史记录，并确保在进行更改时始终创建一个新分支。

 

### 步骤9: 合并PR

继续，然后单击绿色的“合并拉取请求”按钮。这会将你的更改合并到主分支中。

![](https://cdn.jsdelivr.net/gh/reloaded7/zhangzhizhi@2.7/git6.webp.jpg)

当你完成后，我建议你删除你的分支（太多的分支可能会变得混乱），所以也要点击那个灰色的“删除分支”按钮。

你可以通过单击新仓库第一页上的“提交”链接，仔细检查你的提交是否已合并。

![](https://cdn.jsdelivr.net/gh/reloaded7/zhangzhizhi@2.7/git7.webp.jpg)

 这将显示该分支中所有提交的列表。你可以看到我刚刚合并的那个（Merge pull request＃2）。 

![](https://cdn.jsdelivr.net/gh/reloaded7/zhangzhizhi@2.7/git8.webp.jpg)

你还可以在右侧看到提交的[**hash码**](https://git-scm.com/docs/git-hash-object)。Hash码是该特定提交的唯一标识符。它对于引用特定提交和撤消更改（使用 `**[git revert](http://git-scm.com/docs/git-revert)** ` 命令撤回），这非常有用。

 

### 步骤10: 在GitHub上更改回到您的计算机

现在，GitHub上的回购看起来与你在本地机器上的回购略有不同。例如，你在分支中进行的并且合并到主分支的提交在本地计算机的主分支中不存在。

为了获得你或其他人在GitHub上合并的最新更改，请使用该 `**git pull origin master** `命令（在处理master分支时）。



```
mnelson:myproject mnelson$ git pull origin master
remote: Counting objects: 1, done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), done.
From https://github.com/cubeton/mynewrepository
 * branch            master     -> FETCH_HEAD
   b345d9a..5381b7c  master     -> origin/master
Merge made by the 'recursive' strategy.
 mnelson.txt | 1 +
 1 file changed, 1 insertion(+)
```

[view raw](https://gist.github.com/cubeton/48b5c726b496d50c3975/raw/fe2c68e0988c467fd218587e2397552076355b52/pulloriginmaster.md)[pulloriginmaster.md](https://gist.github.com/cubeton/48b5c726b496d50c3975#file-pulloriginmaster-md) hosted with ❤ by [GitHub](https://github.com)



```
mnelson:myproject mnelson$ git pull origin master
remote: Counting objects: 1, done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), done.
From https://github.com/cubeton/mynewrepository
 * branch            master     -> FETCH_HEAD
   b345d9a..5381b7c  master     -> origin/master
Merge made by the 'recursive' strategy.
 mnelson.txt | 1 +
 1 file changed, 1 insertion(+)
```

[view raw](https://gist.github.com/cubeton/48b5c726b496d50c3975/raw/fe2c68e0988c467fd218587e2397552076355b52/pulloriginmaster.md)[pulloriginmaster.md](https://gist.github.com/cubeton/48b5c726b496d50c3975#file-pulloriginmaster-md) hosted with ❤ by [GitHub](https://github.com/)



这将显示已更改的所有文件及其更改方式。

现在我们可以 [**`git log`**](http://git-scm.com/docs/git-log) 再次使用该命令查看所有新提交。

（你可能需要将分支切换回主分支。你可以使用该`**git checkout master** `命令执行此操作。）



```
mnelson:myproject mnelson$ git log
commit 3e270876db0e5ffd3e9bfc5edede89b64b83812c
Merge: 4f1cb17 5381b7c
Author: Meghan Nelson <mnelson@hubspot.com>
Date:   Fri Sep 11 17:48:11 2015 -0400

    Merge branch 'master' of https://github.com/cubeton/mynewrepository

commit 4f1cb1798b6e6890da797f98383e6337df577c2a
Author: Meghan Nelson <mnelson@hubspot.com>
Date:   Fri Sep 11 17:48:00 2015 -0400

    added a new file

commit 5381b7c53212ca92151c743b4ed7dde07d9be3ce
Merge: b345d9a 1e8dc08
Author: Meghan Nelson <meghan@meghan.net>
Date:   Fri Sep 11 17:43:22 2015 -0400

    Merge pull request #2 from cubeton/my-newbranch
    
    Added some more text to my file

commit 1e8dc0830b4db8c93efd80479ea886264768520c
Author: Meghan Nelson <mnelson@hubspot.com>
Date:   Fri Sep 11 17:06:05 2015 -0400

    Added some more text to my file

commit b345d9a25353037afdeaa9fcaf9f330effd157f1
Author: Meghan Nelson <mnelson@hubspot.com>
Date:   Thu Sep 10 17:42:15 2015 -0400

    This is my first commit!
```

[view raw](https://gist.github.com/cubeton/48f55c5a237cd8e1a238/raw/3e31113a073b9bdec16800407d718b631dd0f587/gitlogaftermerge.md)[gitlogaftermerge.md](https://gist.github.com/cubeton/48f55c5a237cd8e1a238#file-gitlogaftermerge-md) hosted with ❤ by [GitHub](https://github.com)



```
mnelson:myproject mnelson$ git log
commit 3e270876db0e5ffd3e9bfc5edede89b64b83812c
Merge: 4f1cb17 5381b7c
Author: Meghan Nelson <mnelson@hubspot.com>
Date:   Fri Sep 11 17:48:11 2015 -0400

    Merge branch 'master' of https://github.com/cubeton/mynewrepository

commit 4f1cb1798b6e6890da797f98383e6337df577c2a
Author: Meghan Nelson <mnelson@hubspot.com>
Date:   Fri Sep 11 17:48:00 2015 -0400

    added a new file

commit 5381b7c53212ca92151c743b4ed7dde07d9be3ce
Merge: b345d9a 1e8dc08
Author: Meghan Nelson <meghan@meghan.net>
Date:   Fri Sep 11 17:43:22 2015 -0400

    Merge pull request #2 from cubeton/my-newbranch
    
    Added some more text to my file

commit 1e8dc0830b4db8c93efd80479ea886264768520c
Author: Meghan Nelson <mnelson@hubspot.com>
Date:   Fri Sep 11 17:06:05 2015 -0400

    Added some more text to my file

commit b345d9a25353037afdeaa9fcaf9f330effd157f1
Author: Meghan Nelson <mnelson@hubspot.com>
Date:   Thu Sep 10 17:42:15 2015 -0400

    This is my first commit!
```

[view raw](https://gist.github.com/cubeton/48f55c5a237cd8e1a238/raw/3e31113a073b9bdec16800407d718b631dd0f587/gitlogaftermerge.md)[gitlogaftermerge.md](https://gist.github.com/cubeton/48f55c5a237cd8e1a238#file-gitlogaftermerge-md) hosted with ❤ by [GitHub](https://github.com/)



### 步骤11：享受你的成果

你已成功制作PR并将代码合并到主分支。恭喜！如果你想更深入地潜水，请查看此Git101文件夹中的文件， 以获取有关使用git和GitHub的更多提示和技巧。

我还建议你花一些时间与你的团队一起模拟像我们这样做的小型团队项目。让你的团队使用你的团队名称创建一个新文件夹，并添加一些带有文本的文件。然后，尝试将这些更改推送到此远程仓库。这样，你的团队就可以开始更改他们最初未创建的文件并使用PR功能进行练习。并且，使用GitHub上的git blame和git history工具来熟悉跟踪文件中的更改以及进行这些更改的人员。 

你使用git的次数越多，使用git就会越熟练。（最后你会离不开它。）