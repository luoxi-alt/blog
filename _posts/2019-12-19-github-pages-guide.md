---
layout: post
title: Git和GitHub入门指南（教程）
tags: [github, tutorial]
description:  "github pages tutorial docs"
excerpt_separator: <!--more-->
---

![img](https://product.hubspot.com/hs-fs/hubfs/Product_Site/Images/HubSpot_Logo_2x.png?width=250&name=HubSpot_Logo_2x.png) 

# ***\*Product\****

**·** [***\*HOME\****](https://product.hubspot.com/)

**·** [***\*JOBS\****](https://www.hubspot.com/jobs/departments/product-and-engineering)

**·** [***\*BLOG\****](https://product.hubspot.com/blog)

**·** [***\*OPEN SOURCE\****](http://github.hubspot.com/?__hstc=90302427.97218259c08d7f8fb8677b6ba30fa505.1567409182088.1567409182088.1567409182088.1&__hssc=90302427.1.1567409182089&__hsfp=1189399445)

# [HUBSPOT PRODUCT AND ENGINEERING BLOG](https://product.hubspot.com/blog)

# ***\*Git和GitHub入门指南（教程）\****

2015年10月1日/作者梅根·尼尔森（Meghan Nelson）

 

· 

· Share

· 

![img](https://product.hubspot.com/hs-fs/hubfs/Git_101-1.jpg?width=310&height=258&name=Git_101-1.jpg)8月，我们在HubSpot主持了“女人密码”聚会，并为初学者主持了有关使用git和GitHub的研讨会。我首先浏览了有关git的基础知识和背景的幻灯片演示，然后我们分成小组来运行我创建的用来模拟大型协作项目的教程。活动结束后我们得到了反馈，它是一个实用的动手介绍。因此，如果您还是git的新手，请按照以下步骤操作，以轻松地更改代码库，打开拉取请求（PR）并将代码合并到master分支中。任何重要的git和GitHub术语均以粗体显示，并带有指向官方git参考资料的链接。

 

### ***\*步骤0：安装git并创建一个GitHub帐户\****

您需要做的前两件事是安装git并创建一个免费的GitHub帐户。

请按照此处的说明安装git（如果尚未安装）。请注意，对于本教程，我们将仅在命令行上使用git。尽管有一些很棒的git GUI（图形用户界面），但我认为先使用git特定的命令学习git，然后在更熟悉该命令后尝试git GUI会更容易。

完成此操作后，在此处创建一个GitHub帐户。 （公共存储库是免费的，但私人存储库是收费的。）

步骤1：建立本地git存放区

使用git在本地计算机上创建新项目时，首先要创建一个新的存储库（或简称为“ repo”）。

要使用git，我们将使用终端。如果您对终端和基本命令没有太多经验，请查看本教程（特别是“导航文件系统”和“移动”部分）。

首先，打开一个终端，然后使用cd（更改目录）命令移动到要在本地计算机上放置项目的位置。例如，如果您的桌面上有一个“项目”文件夹，则可以执行以下操作：

要在文件夹的根目录中初始化git存储库，请运行git init命令：

 

### ***\*步骤1：建立本地git存放区\****

使用git在本地计算机上创建新项目时，首先要创建一个新的存储库（或简称为“ repo”）。

要使用git，我们将使用终端。如果您对终端和基本命令没有太多经验，请查看本教程（特别是“导航文件系统”和“移动”部分）。

首先，打开一个终端，然后使用cd（更改目录）命令移动到要在本地计算机上放置项目的位置。例如，如果您的桌面上有一个“项目”文件夹，则可以执行以下操作：

mnelson:Desktop mnelson$ cd ~/Desktop

mnelson:Desktop mnelson$ mkdir myproject

mnelson:Desktop mnelson$ cd myproject/

[***\*view raw\****](https://gist.github.com/cubeton/67a84eb876984f0b5785/raw/d4560016d742865c1fd68d97fcff1feb557d5e19/terminalcd.md)[***\*terminalcd.md\****](#file-terminalcd-md) hosted with ❤ by [***\*GitHub\****](https://github.com)

mnelson:Desktop mnelson$ cd ~/Desktop

mnelson:Desktop mnelson$ mkdir myproject

mnelson:Desktop mnelson$ cd myproject/

[***\*view raw\****](https://gist.github.com/cubeton/67a84eb876984f0b5785/raw/d4560016d742865c1fd68d97fcff1feb557d5e19/terminalcd.md)[***\*terminalcd.md\****](#file-terminalcd-md) hosted with ❤ by [***\*GitHub\****](https://github.com/)

 

要在文件夹的根目录中初始化git存储库，请运行git init命令：

mnelson:myproject mnelson$ git init

Initialized empty Git repository in /Users/mnelson/Desktop/myproject/.git/

[***\*view raw\****](https://gist.github.com/cubeton/89793ba1bc947f64658e/raw/f3dba1dd72fda5eeb98b761338aedfc310d29d54/gitinit.md)[***\*gitinit.md\****](#file-gitinit-md) hosted with ❤ by [***\*GitHub\****](https://github.com)

mnelson:myproject mnelson$ git init

Initialized empty Git repository in /Users/mnelson/Desktop/myproject/.git/

[***\*view raw\****](https://gist.github.com/cubeton/89793ba1bc947f64658e/raw/f3dba1dd72fda5eeb98b761338aedfc310d29d54/gitinit.md)[***\*gitinit.md\****](#file-gitinit-md) hosted with ❤ by [***\*GitHub\****](https://github.com/)

###  

### ***\*步骤2：将新文件添加到存储库\****

继续，使用您喜欢的任何文本编辑器或运行touch命令将新文件添加到项目中。

在包含git repo的文件夹中添加或修改文件后，git会注意到该repo内部已进行了更改。但是，除非您明确告知git，否则git不会正式跟踪该文件（即，将其放入提交中-接下来我们将详细讨论提交）。

mnelson:myproject mnelson$ touch mnelson.txt

mnelson:myproject mnelson$ ls

mnelson.txt

[***\*view raw\****](https://gist.github.com/cubeton/2d8f224bede4c2dde86b/raw/b865e27cc4715b3a3a4a5839e77ab232ff1b31f9/addfile.md)[***\*addfile.md\****](#file-addfile-md) hosted with ❤ by [***\*GitHub\****](https://github.com)

mnelson:myproject mnelson$ touch mnelson.txt

mnelson:myproject mnelson$ ls

mnelson.txt

[***\*view raw\****](https://gist.github.com/cubeton/2d8f224bede4c2dde86b/raw/b865e27cc4715b3a3a4a5839e77ab232ff1b31f9/addfile.md)[***\*addfile.md\****](#file-addfile-md) hosted with ❤ by [***\*GitHub\****](https://github.com/)

 

创建新文件之后，可以使用git status命令查看git知道哪些文件存在。

mnelson:myproject mnelson$ git status

On branch master

 

Initial commit

 

Untracked files:

 (use "git add <file>..." to include in what will be committed)

 

​	mnelson.txt

 

nothing added to commit but untracked files present (use "git add" to track)

[***\*view raw\****](https://gist.github.com/cubeton/02e849bbffcbea1e9a61/raw/71c93139666a8a4e06795f53c9aec5db95e6019a/gitstatus.md)[***\*gitstatus.md\****](#file-gitstatus-md) hosted with ❤ by [***\*GitHub\****](https://github.com)

mnelson:myproject mnelson$ git status

On branch master

 

Initial commit

 

Untracked files:

 (use "git add <file>..." to include in what will be committed)

 

​	mnelson.txt

 

nothing added to commit but untracked files present (use "git add" to track)

[***\*view raw\****](https://gist.github.com/cubeton/02e849bbffcbea1e9a61/raw/71c93139666a8a4e06795f53c9aec5db95e6019a/gitstatus.md)[***\*gitstatus.md\****](#file-gitstatus-md) hosted with ❤ by [***\*GitHub\****](https://github.com/)

这基本上是说，“嘿，我们注意到您创建了一个名为mnelson的新文件。txt，但除非你使用'git添加'命令，否则我们不会对它做任何事情。”

 

### ***\*An interlude: The staging environment, the commit, and you\****

当您第一次学习git时，最容易混淆的部分之一是登台环境的概念以及它与提交的关系。

提交是您自上次提交以来更改的文件的记录。本质上，您可以修改您的repo(例如，添加一个文件或修改一个文件)，然后告诉git将这些文件放入提交。

提交构成了项目的本质，允许您在任何时候返回到项目的状态。

那么，如何告诉git将哪些文件放入提交呢?这就是临时环境或索引的用武之地。正如在步骤2中所看到的，当您对repo进行更改时，git会注意到文件已经更改，但是不会对其进行任何操作(比如在提交中添加它)。

要将文件添加到提交，首先需要将其添加到暂存环境。为此，可以使用git add <filename>命令(参见下面的步骤3)。</filename>

一旦使用git add命令将所有需要的文件添加到暂存环境中，就可以使用git commitcommand告诉git将它们打包到提交中。

注意:staging环境(也称为“staging”)是对此的新首选术语，但您也可以将其称为“索引”。

###  

### ***\*步骤3:将文件添加到暂存环境\****

使用git Add命令将文件添加到暂存环境中。

如果您重新运行git status命令，您将看到git已经将文件添加到暂存环境中(请注意“要提交的更改”行)。

mnelson:myproject mnelson$ git status

On branch master

 

Initial commit

 

Changes to be committed:

 (use "git rm --cached <file>..." to unstage)

 

​	new file:  mnelson.txt

[***\*view raw\****](https://gist.github.com/cubeton/28f7bea3b232f67e031c/raw/875157cd78d75c23f3f0e29bf0c97989e3d52937/addtostaging.md)[***\*addtostaging.md\****](#file-addtostaging-md) hosted with ❤ by [***\*GitHub\****](https://github.com)

mnelson:myproject mnelson$ git status

On branch master

 

Initial commit

 

Changes to be committed:

 (use "git rm --cached <file>..." to unstage)

 

​	new file:  mnelson.txt

[***\*view raw\****](https://gist.github.com/cubeton/28f7bea3b232f67e031c/raw/875157cd78d75c23f3f0e29bf0c97989e3d52937/addtostaging.md)[***\*addtostaging.md\****](#file-addtostaging-md) hosted with ❤ by [***\*GitHub\****](https://github.com/)

重申一下，该文件还没有添加到提交中，但即将添加。 

### ***\*步骤4:创建提交\****

现在是创建第一个commit的时候了!

运行命令git commit -m“关于提交的消息”

mnelson:myproject mnelson$ git commit -m "This is my first commit!"

[master (root-commit) b345d9a] This is my first commit!

 1 file changed, 1 insertion(+)

 create mode 100644 mnelson.txt

[***\*view raw\****](https://gist.github.com/cubeton/1068d965d147b4039e4d/raw/5c3262c3f6e3c28328ba57ea33c512dbab149fcf/commit.md)[***\*commit.md\****](#file-commit-md) hosted with ❤ by [***\*GitHub\****](https://github.com)

mnelson:myproject mnelson$ git commit -m "This is my first commit!"

[master (root-commit) b345d9a] This is my first commit!

 1 file changed, 1 insertion(+)

 create mode 100644 mnelson.txt

[***\*view raw\****](https://gist.github.com/cubeton/1068d965d147b4039e4d/raw/5c3262c3f6e3c28328ba57ea33c512dbab149fcf/commit.md)[***\*commit.md\****](#file-commit-md) hosted with ❤ by [***\*GitHub\****](https://github.com/)

提交结束时的消息应该与提交所包含的内容相关——可能是新特性，可能是bug修复，也可能只是修复了一个拼写错误。不要写“asdfadsf”或“foobar”这样的信息。那让别人看到你的承诺都很难过。非常,非常,难过。

 

### ***\*步骤5：创建一个新分支\****

现在，您已经进行了新的提交，让我们尝试一些更高级的东西。

假设您要制作一个新功能，但担心在开发功能时对主项目进行更改。这是git分支进入的地方。

分支允许您在项目的“状态”之间来回移动。例如，如果要向网站添加新页面，则可以仅为该页面创建一个新分支，而不会影响项目的主要部分。完成页面后，您可以将分支中的更改合并到master分支中。创建新分支时，Git会跟踪分支“分支”的提交，因此它知道所有文件的历史记录。

假设您在master分支上，并且想要创建一个新分支来开发您的网页。您将执行以下操作：运行git checkout -b <我的分支名称>。该命令将自动创建一个新分支，然后在其上“签出”，这意味着git会将您移至该分支，脱离master分支。

运行上述命令后，可以使用git branch命令来确认您的分支已创建：

mnelson:myproject mnelson$ git branch

 master* my-new-branch

[***\*view raw\****](https://gist.github.com/cubeton/fa25a25f322a2cd5f405/raw/81033788d288adeffe260bd724ab2699b29e3e35/gitbranch.md)[***\*gitbranch.md\****](#file-gitbranch-md) hosted with ❤ by [***\*GitHub\****](https://github.com)

mnelson:myproject mnelson$ git branch

 master* my-new-branch

[***\*view raw\****](https://gist.github.com/cubeton/fa25a25f322a2cd5f405/raw/81033788d288adeffe260bd724ab2699b29e3e35/gitbranch.md)[***\*gitbranch.md\****](#file-gitbranch-md) hosted with ❤ by [***\*GitHub\****](https://github.com/)

分支名称旁边带有星号表示在给定时间指向的分支。

现在，如果您切换回master分支并进行更多提交，则在将这些更改合并到新分支之前，您的新分支将看不到任何更改。

 

### ***\*步骤6：在GitHub上创建一个新的存储库\****

如果只想在本地跟踪代码，则无需使用GitHub。但是，如果您想与团队合作，则可以使用GitHub协同修改项目的代码。

要在GitHub上创建新的仓库，请登录并转到GitHub主页。您应该看到一个绿色的“ +新存储库”按钮：

![img](https://product.hubspot.com/hs-fs/hubfs/Git_101_Screenshot1-2.png?width=671&height=141&name=Git_101_Screenshot1-2.png) 

 

 

 

 

 

单击按钮后，GitHub将要求您命名您的存储库并提供简短描述：

![img](https://product.hubspot.com/hs-fs/hubfs/Git_101_Screenshot_2-1.png?width=671&height=418&name=Git_101_Screenshot_2-1.png) 

 

 

 

 

 

 

 

 

 

 

 

 

填写完信息后，按“创建存储库”按钮创建新的存储库。

GitHub会询问您是否要从头开始创建新的存储库，或者是否要添加在本地创建的存储库。在这种情况下，由于我们已经在本地创建了新的存储库，因此我们希望将其推送到GitHub上，因此请遵循“ ....或从命令行推送现有存储库”部分：

mnelson:myproject mnelson$ git remote add origin https://github.com/cubeton/mynewrepository.git

mnelson:myproject mnelson$ git push -u origin master

Counting objects: 3, done.

Writing objects: 100% (3/3), 263 bytes | 0 bytes/s, done.

Total 3 (delta 0), reused 0 (delta 0)

To https://github.com/cubeton/mynewrepository.git

 \* [new branch]    master -> master

Branch master set up to track remote branch master from origin.

[***\*view raw\****](https://gist.github.com/cubeton/3a2616c44e35ca68a6b0/raw/41e5758cfdbd7db8a1659c1adaba9346680097f9/addgithub.md)[***\*addgithub.md\****](#file-addgithub-md) hosted with ❤ by [***\*GitHub\****](https://github.com)

mnelson:myproject mnelson$ git remote add origin https://github.com/cubeton/mynewrepository.git

mnelson:myproject mnelson$ git push -u origin master

Counting objects: 3, done.

Writing objects: 100% (3/3), 263 bytes | 0 bytes/s, done.

Total 3 (delta 0), reused 0 (delta 0)

To https://github.com/cubeton/mynewrepository.git

 \* [new branch]    master -> master

Branch master set up to track remote branch master from origin.

[***\*view raw\****](https://gist.github.com/cubeton/3a2616c44e35ca68a6b0/raw/41e5758cfdbd7db8a1659c1adaba9346680097f9/addgithub.md)[***\*addgithub.md\****](#file-addgithub-md) hosted with ❤ by [***\*GitHub\****](https://github.com/)

 （由于您的GitHub用户名和存储库名称不同，因此您需要将第一个命令行中的URL更改为本节中GitHub列出的内容。）

 

### ***\*步骤7：推送分支到GitHub\****

现在我们将把您分支中的提交推送到您的新GitHub repo。这允许其他人看到你所做的更改。如果它们得到了存储库所有者的批准，那么这些更改可以合并到主分支中。

要将更改推送到GitHub上的新分支上，您需要运行git push origin您的分支名称。GitHub将在远程存储库上自动为您创建分支：

mnelson:myproject mnelson$ git push origin my-new-branch

Counting objects: 3, done.

Delta compression using up to 8 threads.

Compressing objects: 100% (2/2), done.

Writing objects: 100% (3/3), 313 bytes | 0 bytes/s, done.

Total 3 (delta 0), reused 0 (delta 0)

To https://github.com/cubeton/mynewrepository.git

 \* [new branch]    my-new-branch -> my-new-branch

[***\*view raw\****](https://gist.github.com/cubeton/bf8274609c344b6d0e70/raw/4764e740cac9a48eefad341d9e34ceb09f89b73f/addnewbranchgithub.md)[***\*addnewbranchgithub.md\****](#file-addnewbranchgithub-md) hosted with ❤ by [***\*GitHub\****](https://github.com)

mnelson:myproject mnelson$ git push origin my-new-branch

Counting objects: 3, done.

Delta compression using up to 8 threads.

Compressing objects: 100% (2/2), done.

Writing objects: 100% (3/3), 313 bytes | 0 bytes/s, done.

Total 3 (delta 0), reused 0 (delta 0)

To https://github.com/cubeton/mynewrepository.git

 \* [new branch]    my-new-branch -> my-new-branch

[***\*view raw\****](https://gist.github.com/cubeton/bf8274609c344b6d0e70/raw/4764e740cac9a48eefad341d9e34ceb09f89b73f/addnewbranchgithub.md)[***\*addnewbranchgithub.md\****](#file-addnewbranchgithub-md) hosted with ❤ by [***\*GitHub\****](https://github.com/)

您可能想知道“origin”这个词在上面的命令中是什么意思。当您将远程存储库克隆到本地计算机时，git会为您创建一个别名。几乎在所有情况下，这个别名都被称为“origin”，实际上是远程存储库URL的简写。因此，要将更改推送到远程存储库，可以使用以下命令：git push git@github.com:git/git.git 您的分支名称或git push origin 您的分支名称

（如果这是您第一次在本地使用GitHub，它可能会提示您使用GitHub用户名和密码登录。）

如果您刷新GitHub页面，您将看到一条一个名为您的分支刚刚被推送到存储库中的注释。您还可以单击“branches”链接，查看您的分支列表。

![img](https://product.hubspot.com/hs-fs/hubfs/Git_101_Screenshot2.png?width=869&height=183&name=Git_101_Screenshot2.png) 

现在点击上面屏幕截图中的绿色按钮。我们要pull request！

 

### ***\*步骤8：创建一个Pull Request\****

Pull request (或PR)是提醒仓库所有者希望对其内容进行某些更改的方法。它允许其他人在将更改放在主分支上之前检查内容并确保内容无误。

这是您提交PR之前的页面：

![img](https://product.hubspot.com/hs-fs/hubfs/Git_101_Screenshot_4.png?width=869&height=548&name=Git_101_Screenshot_4.png) 

 

这就是您提交PR申请后的情况：

![img](https://product.hubspot.com/hs-fs/hubfs/Git_101_Screenshot_5.png?width=869&height=557&name=Git_101_Screenshot_5.png) 

 

您可能会在底部看到一个绿色的选项，上面写着“Merge pull request”。单击此项意味着您将把更改合并到主分支中。

注意这个选项不一定是绿色的。在某些情况下，它将是灰色的，这意味着你面临一个合并冲突。当一个文件中的更改与另一个文件中的更改冲突时，git无法确定要使用哪个版本。您必须手动进入并告诉git使用哪个版本。

有时你会成为这个仓库的共同所有人或唯一所有人，在这种情况下，你可能不需要创建PR来合并你的更改。但是，创建一个分支仍然是一个好方法，这样您可以保留更新的更完整历史记录，并确保在进行更改时始终创建一个新分支。

 

### ***\*步骤\*******\*9\*******\*：合并PR\****

点击绿色的“合并请求”按钮。将您的更改合并到master分支中。

![img](https://product.hubspot.com/hs-fs/hubfs/Git_101_Screenshot_6.png?width=869&height=519&name=Git_101_Screenshot_6.png) 

 

完成后，建议您删除分支（太多分支会变得凌乱），因此请点击灰色的“删除分支”按钮。

您可以通过单击新存储库首页上的“提交”来再次检查提交是否已合并。

![img](https://product.hubspot.com/hs-fs/hubfs/Git_101_Screenshot_7.png?width=869&height=222&name=Git_101_Screenshot_7.png) 

 

这将显示该分支中所有提交的列表。您可以看到刚刚合并的那个（合并请求2）。

![img](https://product.hubspot.com/hs-fs/hubfs/Git_101_Screenshot_8.png?width=869&height=370&name=Git_101_Screenshot_8.png) 

您还可以在右侧看到提交的哈希码。哈希码是该特定提交的唯一标识符。这对于引用特定的提交以及撤消更改很有用（使用git revert <hash code number>命令撤销）。

 

### ***\*步骤\*******\*10\*******\*：将GitHub上的更改返回到您的计算机\****

现在，GitHub上的仓库看起来与本地计算机上的仓库有所不同。例如，您在分支中进行的提交并合并到master分支中的提交在本地计算机上的master分支中不存在。

为了获得您或其他人在GitHub上合并的最新更改，请使用git pull origin master命令（在master分支上操作）。

mnelson:myproject mnelson$ git pull origin master

remote: Counting objects: 1, done.

remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0

Unpacking objects: 100% (1/1), done.

From https://github.com/cubeton/mynewrepository

 \* branch       master   -> FETCH_HEAD

  b345d9a..5381b7c  master   -> origin/master

Merge made by the 'recursive' strategy.

 mnelson.txt | 1 +

 1 file changed, 1 insertion(+)

[***\*view raw\****](https://gist.github.com/cubeton/48b5c726b496d50c3975/raw/fe2c68e0988c467fd218587e2397552076355b52/pulloriginmaster.md)[***\*pulloriginmaster.md\****](#file-pulloriginmaster-md) hosted with ❤ by [***\*GitHub\****](https://github.com)

mnelson:myproject mnelson$ git pull origin master

remote: Counting objects: 1, done.

remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0

Unpacking objects: 100% (1/1), done.

From https://github.com/cubeton/mynewrepository

 \* branch       master   -> FETCH_HEAD

  b345d9a..5381b7c  master   -> origin/master

Merge made by the 'recursive' strategy.

 mnelson.txt | 1 +

 1 file changed, 1 insertion(+)

[***\*view raw\****](https://gist.github.com/cubeton/48b5c726b496d50c3975/raw/fe2c68e0988c467fd218587e2397552076355b52/pulloriginmaster.md)[***\*pulloriginmaster.md\****](#file-pulloriginmaster-md) hosted with ❤ by [***\*GitHub\****](https://github.com/)

这将向您显示所有已更改的文件及其更改方式。

现在我们可以再次使用git log命令查看所有新提交。

（您可能需要将分支切换回master分支。您可以使用git checkout master命令来完成。）

mnelson:myproject mnelson$ git log

commit 3e270876db0e5ffd3e9bfc5edede89b64b83812c

Merge: 4f1cb17 5381b7c

Author: Meghan Nelson <mnelson@hubspot.com>

Date:  Fri Sep 11 17:48:11 2015 -0400

 

  Merge branch 'master' of https://github.com/cubeton/mynewrepository

 

commit 4f1cb1798b6e6890da797f98383e6337df577c2a

Author: Meghan Nelson <mnelson@hubspot.com>

Date:  Fri Sep 11 17:48:00 2015 -0400

 

  added a new file

 

commit 5381b7c53212ca92151c743b4ed7dde07d9be3ce

Merge: b345d9a 1e8dc08

Author: Meghan Nelson <meghan@meghan.net>

Date:  Fri Sep 11 17:43:22 2015 -0400

 

  Merge pull request #2 from cubeton/my-newbranch

  

  Added some more text to my file

 

commit 1e8dc0830b4db8c93efd80479ea886264768520c

Author: Meghan Nelson <mnelson@hubspot.com>

Date:  Fri Sep 11 17:06:05 2015 -0400

 

  Added some more text to my file

 

commit b345d9a25353037afdeaa9fcaf9f330effd157f1

Author: Meghan Nelson <mnelson@hubspot.com>

Date:  Thu Sep 10 17:42:15 2015 -0400

 

  This is my first commit!

[***\*view raw\****](https://gist.github.com/cubeton/48f55c5a237cd8e1a238/raw/3e31113a073b9bdec16800407d718b631dd0f587/gitlogaftermerge.md)[***\*gitlogaftermerge.md\****](#file-gitlogaftermerge-md) hosted with ❤ by [***\*GitHub\****](https://github.com)

mnelson:myproject mnelson$ git log

commit 3e270876db0e5ffd3e9bfc5edede89b64b83812c

Merge: 4f1cb17 5381b7c

Author: Meghan Nelson <mnelson@hubspot.com>

Date:  Fri Sep 11 17:48:11 2015 -0400

 

  Merge branch 'master' of https://github.com/cubeton/mynewrepository

 

commit 4f1cb1798b6e6890da797f98383e6337df577c2a

Author: Meghan Nelson <mnelson@hubspot.com>

Date:  Fri Sep 11 17:48:00 2015 -0400

 

  added a new file

 

commit 5381b7c53212ca92151c743b4ed7dde07d9be3ce

Merge: b345d9a 1e8dc08

Author: Meghan Nelson <meghan@meghan.net>

Date:  Fri Sep 11 17:43:22 2015 -0400

 

  Merge pull request #2 from cubeton/my-newbranch

  

  Added some more text to my file

 

commit 1e8dc0830b4db8c93efd80479ea886264768520c

Author: Meghan Nelson <mnelson@hubspot.com>

Date:  Fri Sep 11 17:06:05 2015 -0400

 

  Added some more text to my file

 

commit b345d9a25353037afdeaa9fcaf9f330effd157f1

Author: Meghan Nelson <mnelson@hubspot.com>

Date:  Thu Sep 10 17:42:15 2015 -0400

 

  This is my first commit!

[***\*view raw\****](https://gist.github.com/cubeton/48f55c5a237cd8e1a238/raw/3e31113a073b9bdec16800407d718b631dd0f587/gitlogaftermerge.md)[***\*gitlogaftermerge.md\****](#file-gitlogaftermerge-md) hosted with ❤ by [***\*GitHub\****](https://github.com/)

### ***\*步骤11：沉浸在git的荣耀中\****

您已成功进行PR，并将您的代码合并到master分支中。恭喜你！如果您想更深入一点，请查看此Git101文件夹中的文件，以获取有关使用git和GitHub的更多提示和技巧。

建议您花一些时间与您的团队一起模拟一个较小的小组项目，就像在这里操作的那样。让您的团队用您的团队名称创建一个新文件夹，并向其中添加一些文本文件。然后，尝试将这些更改推送到此远程仓库中。这样，您的团队可以开始对最初没有创建的文件进行更改并使用PR功能进行练习。然后，使用GitHub上的git blame和git历史记录工具熟悉跟踪文件中进行了哪些更改以及谁进行了这些更改。

您使用git的次数越多，您将越感到舒适。 （我抗拒不了。）

![img](file:///C:/Users/Administrator/Desktop/translation-project/%E9%99%84%E4%BB%B62%20translation%20project/An%20Intro%20to%20Git%20and%20GitHub%20for%20Beginners%20(Tutorial)_files/0027c58.webp) 

### ***\*由梅根·尼尔森（Meghan Nelson）撰写\****

### ***\*SUBSCRIBE FOR UPDATES\****

窗体顶端



HubSpot Product needs the contact information you provide to us to contact you about our products and services. You may unsubscribe from these communications at anytime. For information on how to unsubscribe, as well as our privacy practices and commitment to protecting your privacy, check out our Privacy Policy.

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml6920\wps13.wmf)

窗体底端

### ***\*TOPICS\****

· [PRODUCT](https://product.hubspot.com/blog/topic/product)

· [ENGINEERING](https://product.hubspot.com/blog/topic/engineering)

· [DESIGN](https://product.hubspot.com/blog/topic/design)

· [PRODUCT MANAGEMENT](https://product.hubspot.com/blog/topic/product-management)

· [UX](https://product.hubspot.com/blog/topic/ux)

· [CULTURE](https://product.hubspot.com/blog/topic/culture)

· [CAREER GROWTH](https://product.hubspot.com/blog/topic/career-growth)

![img](file:///C:/Users/Administrator/Desktop/translation-project/%E9%99%84%E4%BB%B62%20translation%20project/An%20Intro%20to%20Git%20and%20GitHub%20for%20Beginners%20(Tutorial)_files/0ee48652-14c2-4be1-ae50-b7d56578e6be.webp) 

[What is HubSpot](https://www.hubspot.com/what-is-hubspot)|[Our Story](https://www.hubspot.com/internet-marketing-company)|[Our Products](https://www.hubspot.com/products)|[Culture Code](https://blog.hubspot.com/blog/tabid/6307/bid/34234/The-HubSpot-Culture-Code-Creating-A-Company-We-Love.aspx)

[Facebook](https://www.facebook.com/HubSpotDevelopment?fref=ts)|[Twitter](https://twitter.com/HubSpotDev)|[Instagram](https://instagram.com/hubspotdev/)
