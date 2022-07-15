

# HCIE R&S

1.二层

# GIT的使用

#### 1.安装git

在Windows上使用Git，可以从Git官网直接下载安装程序，然后按默认选项安装即可。

安装完成后，在开始菜单里找到“Git”->“Git Bash”，蹦出一个类似命令行窗口的东西，就说明Git安装成功！

#### 2.配置git

配置用户名：

```shell
git config --global user.name "Your Name"
```

配置账号：

```shell
$ git config --global user.email "email@example.com"
```

在git上创建SSH Key，首先进入.ssh目录

```shell
 cd ~/.ssh
 ssh-keygen -t rsa –C “youremail@example.com” --邮箱
```

得到ssh的公钥和私钥，将公钥复制到github上



#### 3.创建文件夹（本地仓库）

通过`git init`命令把这个目录变成Git可以管理的仓库

将文件推送到本地仓库

```shell
git add .

git commit -m "描述信息"
```



#### 3.github创建仓库



将仓库的SSH链接复制到git



#### 4.上传代码

初次推送代码

```
git add .
git commit -m "描述信息"
git branch -M main
git remote add origin git@github.com:LiangTman/-.git
git push -u origin main
```

也可创建分支，在分支上操作

```shell
创建dev分支
git branch dev
git checkout dev --切换到dev分区
git add .
git commit -m ""
git checkout main --切换到主分支
git merge dev --合并分支
git add .
git commit -m ""
git push
```



#### 5.拉取代码

git pull

可以克隆别人的仓库

```shell
git clone git@github.com:LiangTman/-.git
```

