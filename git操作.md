# 配置
## 1. 安装git
- Windows 平台上安装, [下载链接](https://npm.taobao.org/mirrors/git-for-windows/v2.30.0.windows.1/Git-2.30.0-64-bit.exe)
## 2. git 与 github配置
- 参考文章：[Git的使用以及GitHub的配置
](https://www.jianshu.com/p/6ae3697a7c93)
### 1) git配置
- 安装好git后，在任意文件夹，都可以右键，点"git bash here"打开git终端，在此可以输入git指令
- git初始设置,指令如下，自己修改自己相应用户名、邮箱
```
git config --global user.name WangYb
git config --global user.email wangyb@xiaoma.cn //配置本地
```

- SSH Key公钥的生成

打开终端输入:
```
ssh-keygen -t rsa -C "wangyb@xiaoma.cn" //记得改自己邮箱
```
一路回车即可(中间有提示让输入密码,可跳过),然后到
> /Users/你的电脑名/.ssh/

下找到并打开**id_rsa.pub**就是生产的公钥（友情提示，右键->打开方式->记事本），==一会github上配置要用==



### 2) github初始操作

#### a)注册GitHub账号
[官网](https://github.com/)
- 用你上面配置时用的邮箱注册一个账号，用户名随意，反正咱们自己用，你起一个咱们一看就知道是谁的名字就行（比如我的：WangDachui2021）
- 经过验证后，看到"Welcome to GitHub"后，随便选
- Please verify your email address 到自己邮箱找，点验证的按钮
- github注册就可以了

#### b) 配置公钥（具体如果不会，看上面参考文章，有图）
github网站 -> 右上角头像 -> settings -> SSH and GPG keys -> New SSH key -> title随意，key就复制我们**id_rsa.pub**里的字符
- 注意一会github会给你发邮件确认，确认下就行了。
- 本地测试连接
```
在git Bash 中输入以下代码
$ ssh -T git@github.com
有提示输入yes即可
```
看结果里
```
Warning: Permanently added 'github.com,13.229.188.59' (RSA) to the list of known hosts.
ssh_dispatch_run_fatal: Connection to 13.229.188.59 port 22: Software caused connection abort
```
就没啥问题

```
以下是创建仓库的人要关注的事，没你事就不看！
#### c) 创建属于自己的仓库
#### d) 配置仓库信息
#### e) 完成配置
#### f) 托管自己的项目
```
# 协作时操作
参考文档

[git - 简易指南](https://www.bootcss.com/p/git-guide/)

[我用四个命令概括了 Git 的所有套路](https://labuladong.gitbook.io/algo/di-wu-zhang-ji-shu-wen-zhang-xi-lie/git-chang-yong-ming-ling)

### 1. clone 克隆
到github上找到我们项目
[项目地址](https://github.com/WangDachui2021/XMW_HomeworkVideo)
看到绿色"code"，点开，选"SSH",复制那个链接
>  git@github.com:WangDachui2021/XMW_HomeworkVideo.git

到本地一个方便放项目的地方右键终端执行
```
git clone git@github.com:WangDachui2021/XMW_HomeworkVideo.git  //克隆网站上的项目
```
如果有问你啥yes/no，就输入yes就行

### 2. 平时的操作
本地仓库下，右键git bash
#### 1) git pull //更新你的本地仓库至最新改动
#### 2) git add .
> git add . //. 表示 当前文件夹下所有改动/添加的文件
#### 3) git commit -m "代码提交信息"
> 比如 git commit -m "第13-15课"
#### 4) git push