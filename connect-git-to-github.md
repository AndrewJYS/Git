# Git常用操作  

以win10为例  

## 下载安装Git  

进入 [Git官网](https://git-scm.com/downloads)，找到对应版本下载安装

## 配置SSH和基本信息  

打开Git Bash，输入下述命令即可在本地生成密钥，引号内加入注册Github的邮箱  

```md
ssh-keygen -t rsa -C ""
```

进入Git Bash返回的SSH文件地址，打开该文件；将内容复制到GitHub的[SSH key](https://github.com/settings/ssh/new)并生成密钥，该密钥只要不更换，在以后的其他任何仓库使用中，不需要重新设置。使用下述命令验证是否已配置好SSH  

```md
ssh -T git@github.com
```

接着配置用户名和用户邮箱，引号内分别填写用户名和用户邮箱  

```md
git config --global user.name ""
git config --global user.email ""
```

如果要验证刚才所配置信息是否完整，则可以输入下述命令  

```md
git config --global user.name
git config --global user.email
```

## 初始化本地仓库，并连接到github  

选择建立Git仓库的文件夹，右击文件夹，选择 Git Bash Here，输入下述命令初始化Git仓库。该命令将创建一个名为 .git 的子目录，这个子目录含有你初始化的 Git 仓库中所有的必须文件。但是，在这个时候，我们仅仅是做了一个初始化的操作，你的项目里的文件还没有被跟踪。  

```md
git init
```

在Github新建仓库，复制该仓库SSH，使用下述命令，将本地仓库与github相连  

```md
git remote add origin 后面填写github新建的仓库的SSH
```

## 克隆现有的仓库  

如果你想获得一份已经存在了的 Git 仓库的拷贝，则使用git clone命令，例子如下  

```md
git clone https://github.com/AndrewJYS/Git.git
```

## 本地仓库常用操作  

1.跟踪新文件  
使用命令 git add 开始跟踪一个文件，如果要跟踪test.txt，则使用下述命令  

```md
git add test.txt
git add *.txt //跟踪所有.txt格式的文件
```

2.检查当前文件状态  
可以用 git status 命令查看哪些文件处于什么状态。git status 命令的输出十分详细，但其用语有些繁琐。如果你使用 git status -s 命令或 git status --short 命令，你将得到一种格式更为紧凑的输出。  

3.提交更新  
提交命令 git commit。你也可以在 commit 命令后添加 -m 选项，将提交信息与命令放在同一行，如下所示：  

```md
git commit -m 'create test.txt'
```

4.移除文件  
从已跟踪文件清单中移除（确切地说，是从暂存区域移除）某文件。 用 git rm 命令完成此项工作，**并连带从工作目录中删除指定的文件**，这样以后就不会出现在未跟踪文件清单中了。

```md
git rm test.txt
git rm -f test.txt //可以加上-f强制执行
```

另一种情况是，我们想把文件从 Git 仓库中删除（亦即从暂存区域移除），但仍然希望保留在当前工作目录中。 可以使用 --cached 选项：  

```md
git rm --cached *.txt
```

5.查看提交历史  

```md
git log
```

## 远程仓库操作  

1.推送到远程仓库  

```md
git push origin master
```

2.从远程仓库中抓取与拉取  

```md
git pull origin master
git fetch origin
```


## 参考  

[git文档](https://git-scm.com/book/)
