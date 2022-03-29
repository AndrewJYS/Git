# git常用操作
以win10为例  

## 下载git  
进入 [git官网](https://git-scm.com/downloads)，找到对应版本下载安装

## 配置SSH，连接git和github  
打开git bash，输入下述命令即可在本地生成密钥，引号内加入注册github的邮箱
```
ssh-keygen -t rsa -C ""
```
进入git bash返回的ssh文件地址，打开该文件；将内容复制到GitHub的SSH key并生成密钥（https://github.com/settings/ssh/new），
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
git config --global user.name ""
git config --global user.email ""
```

## 初始化仓库  
选择建立git仓库的文件夹，右击文件夹，选择 Git Bash Here  
输入下述命令初始化git仓库
```
git init
```
