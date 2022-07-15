

# 数通



#### 链路聚合

##### 锐捷交换机的链路聚合

###### 1.配置静态链路聚合

通过手工添加 AP 口成员，将多个物理端口绑定，以实现链路聚合。聚合后的逻辑链路带宽是成员链路带宽的总和。	

```
interface aggregateport ap-number  --ap-number：AP 接口编号
```

<!-- 全局配置模式下，用户可以通过 interfaces aggregateport 配置命令创建一个以太网 AP 口。用户可以在
全局配置模式下，通过 no interfaces aggregateport ap-number 删除指定的以太网 AP 口。-->

<!--用户可以通过在指定以太网端口的接口模式下，执行 port-group 命令将物理端口加入一个静态 AP；如果该 AP 不存在， 则同时自动创建这个 AP 口。 用户也可以通过在指定物理端口的接口模式下，执行 port-group mode 命令将物理端口加入一个 LACP AP；如果该 AP 不存在，则同时自动创建这个 AP 口。 配置 AP 功能时，需要在链路两端的设备上都配置，且需要配置相同的 AP 类型(静态 AP 或者 LACP)。-->

```
port-group ap-number --ap-number : AP 接口编号
```

###### 2.配置LACP链路聚合

将指定的物理端口配置为 LACP 成员口。在支持 LACP 功能的设备上配置。使用 LACP 功能时需要配置对应的 LACP 成 员口。

```
port-group key-number mode { active | passive }
```

<!--Key-number :为聚合组的管理 key，Key-number 取值范围根据不同产品支持的聚合组数量不同而变，这个 Key-number 值就是对应的 LACP AP 口的端口号。-->

 active:表示端口以主动模式加入动态聚合组

 passive:模式表示端口以被动模式加入聚合组

<!--为保证 LACP 功能正常，在链路两端的设备上需要对称配置 LACP 成员口。-->



# 软件工具



## GIT的使用

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

