## Git

### 代码量不多，没有必要备份

### 什么是Git?
  - Git是一款源代码管理工具(版本控制工具)
    - 我们写的代码需要使用Git进行管理。
  - 手写的代码
  - 源代码有必要管理起吗？
  - svn,vcs,vss
  - 有必要，因为人工的去处理不同的版本，做相应备份会很麻烦。

  -Git是linux之父当年为了维护linux---linus之前也是手动维护合并把文件发给Linus
  - BitKeeper(收费)
  - 有人想破解(不给提供免费使用)
  - linus自己写了一个版本管理的工具（Git）


### 分布式，集中式
  - 分布式版本管理工具   可以在本地提交.
  

### git提交代码流程 
  1.首先把代码添加到暂存区
    + 命令: `git add [文件路径]`
  2.把代码从暂存区提交到仓库
    + 命令: `git commit -m "[一些注释]"`
  3.可以配合`git status`命令来使用.

### git自报家门
  - 命令:`git config user.name "testName" `
    + 这个命令是用来配置用户名的
  - 命令:`git config user.email "test@isc.com"`
    + 这个命令是用来配置用户邮箱的.

  - 如果需要进行全局配置，直接加上--global参数就可以
    + `git config --global user.name "testName"`
  - 查看配置信息
    + `git config --list`

### cd
  change directory

### git中的忽略文件的配置
  - 在.git隐藏目录所在目录创建一个名为.gitingore的文件，在该文件中配置忽略信息
  >  /tmp.txt    # 表示忽略根目录的tmp.txt文件
     /js/*.js    # 忽略js目录下所有js文件.

### 简写命令
  - 批量添加代码到暂存区
    + 命令:`git add .`
      * 这里的.表示当前目录下的所有文件
  - 一次性把代码提交到仓库
    + `git commit -a  -m "这是合并操作"`
    
    *注意*，如果是文件刚刚新建的文件，不能够使用这种简写方式，必需先使用原先的方式提交一次.


### git日志
  - 命令:`git log`
    + 可以查看提交日志
    + 也可以使用`git log --oneline`查看简洁的信息

### git 版本回退
  - 命令: `git reset --hard Head~0`
    + 这里将代码回退到指定的版本，Head永远表示最近的一次提交。Head~0表示最近一次提交，然后Head~1表示最近一次提交前一次。Head~0可以简写成Head

## git命令回顾
  - `git init` 初始化git仓库
  - `git add [文件路径]` 将代码放到暂存区
  - `git commit -m "[注释]"`将暂存区的代码放到仓库中
  - `git status` 查看工作区状态
  - `git commit -a -m "[注释]"`  合并add 与commit 命令//对与刚创建的文件，没有提交过的无效.
  - `git add .` 批量将文件添加到暂存区
  - .gitignore,在.git目录的同一级创建文件文件，文件中每一行可以配置想要忽略的文件/文件夹的路径;
    + /test.txt
    + /js/*.js
  - `git log` `git log --oneline` 显示所有提交的日志
  - `git reset --hard Head~0` 回退到最后一次提交.

### git reflog命令
  - 可以查看每一次对版本的操作。

### git diff 对比文件差异
  - 命令:`git diff [版本号1] [版本号2] [想要对比的文件路径]`
  - 命令:`git diff`比较工作区与暂存区文件的差异

## git 分支
### 创建分支
  －　命令：｀git　branch　［分支名］｀　创建分支
  －　查看所有分支：｀git　branch｀

### 切换分支
  －　命令：｀git　checkout　［分支名］｀

### 合并分支
  - 命令:`git merge [分支名]`,把指定的分支合并到当前分支

### 删除分支
  - 命令:`git branch -d [分支名]`.

### 解决冲突
  - 如果遇到冲突需要手动处理。

### 创建并切换分支简写
  - `git checkout -b [分支名] `
  - .net vs 2013;//

## github

- 注册账号

### github与git
  - github是一个网站, 提供了git服务器的功能
  - git是版本管理工具

### 上传代码到git服务器上

### 推到服务器上(push)
  - 一个仓库是300M。
  - 命令:`git push [地址] [服务器上的分支名]`
    + 示例:`git push https://github.com/huoqishi/test110.git master`


### git clone
  - 就相当于右键另存为,把项目中的代码下载下来.
  - 命令:`git clone [地址] [可以起个文件夹名]`
    + 示例:`git clone https://github.com/huoqishi/test110.git test`


### 从服务器上拉取代码(pull)
  - 有个条件，执行命令的目录必需有个仓库

### 使用github搭建个人博客
  - gh-pages,如果把代码上传到这个分支上就可以使用浏览器渲染访问。
  - 访问的地址形式:`[github用户名]github.io/[仓库名]/[具体的文件或者路径]`

### 创建远程服务器地址变量 
  - 命令:`git remote add [变量名] [变量值]`
  - 创建之后就可以使用这个变量来代替地址使用.

  - 在push时还可以加上-u参数，表示当前分支与指定的分支进行关联，下次push就不需要指定分支名了。

```javascript
  var name = "小明"
```


### 工具
 - shadowsock
 - http://bandwagonhost.com/


## 命令总结
   - git init
   - git add
   - git commit
   - git status
   - git commit -a -m
   - git config user.name "xxx"
   - git config --list
   - git log --oneline
   - git reset --hard Head~0
   - git reset --hard 版本号
   - git reflog 
   - git diff [] []  [文件路径]
   - git branch dev
   - git checkout dev   // git checkout -b dev
   - git merge dev
   - git branch -d dev
   - git push [地址] [分支名]
   - git pull [地址]


