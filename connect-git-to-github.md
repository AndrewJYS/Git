# Git常用操作
以win10为例  

## 下载Git  
进入 [Git官网](https://git-scm.com/downloads)，找到对应版本下载安装

## 配置SSH，和基本信息  
打开Git Bash，输入下述命令即可在本地生成密钥，引号内加入注册Github的邮箱
```
ssh-keygen -t rsa -C ""
```
进入Git Bash返回的SSH文件地址，打开该文件；将内容复制到GitHub的SSH key并生成密钥（https://github.com/settings/ssh/new），
该密钥只要不更换，在以后的其他任何仓库使用中，不需要重新设置。使用下述命令验证是否已配置好SSH 
```
ssh -T git@github.com
```
接着配置用户名和用户邮箱，引号内分别填写用户名和用户邮箱
```
git config --global user.name ""
git config --global user.email ""
```
如果要验证刚才所配置信息是否完整，则可以输入下述命令
```
git config --global user.name
git config --global user.email
```

## 初始化本地仓库，并连接到github 
选择建立Git仓库的文件夹，右击文件夹，选择 Git Bash Here，输入下述命令初始化Git仓库
```
git init
```
在Github新建仓库，复制该仓库SSH，使用下述命令，将本地仓库与github相连  
```
git remote add origin 后面填写github新建的仓库的SSH
```

## 常用的操作 
```
git add .    添加文件到暂存区
git status   查看当前仓库状态
git log      查看历史提交记录
git rm -f    删除工作区文件
```
