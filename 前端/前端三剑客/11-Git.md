# git

## 版本控制系统

* 版本控制是一种记录一个或若干文件内容变化，以便将来查阅特定版本修订情况的系统
* 作用：
  1. 记录（项目）文件变化
  2. 查看记录信息
  3. 将文件切换到记录时的状态

## 安装Git

* 

## Git配置用户信息

* 设置用户名和邮件地址
  * 设置全局用户名
    * git config --global user.name "用户名"
  * 设置全局邮箱
    * git config --global user.email "邮箱"
* 查看配置
  * git config --list
  * 信息太多可以输入q退出

## git仓库

* 通常有两种获取Git项目仓库的方式
  1. 将尚未进行版本控制的本地目录转为Git仓库（初始化仓库）
  2. 从其他服务器克隆一个已存在的仓库

* 本地初始化Git仓库
  * 新建文件夹并在文件夹下打开 git bash
  * 在git bash 中输入命令Git init 初始化Git仓库

## 记录每次更新到仓库

* 每当完成了一个阶段的目标，想要记录下它时，就将它提交到仓库
* 核心操作
  * 工作区开发
  * 将修改后的文件添加到暂存区
    * git add . 添加所有修改文件
  * 将暂存区的文件记录到版本库
    * git commit -m '信息'

## 查看及切换历史版本

* 查看历史版本
  * git log --oneline 查看简略信息
  * git log 查看全部信息
* 切换历史版本
  * git resert --hard 版本号

* 拓展
  * 终端清屏
    * clear
  * 查看完整历史
    * git reflog

##  Git 忽略文件

* .gitignore 忽略文件
  * 语法：
    * \# 注释
    * 写什么文件名就忽略什么文件
    * .文件名 忽略文件夹
    * \*.扩展名 忽略结尾时扩展名的所有文件
    * 文件夹名/文件名 忽略文件夹下的文件

## 查看文件状态

* git status 查看文件状态
  * 红色：工作区有文件更改
  * 绿色：暂存区有文件更改
  * nothing to commit：没有文件更改

## Git分支

* 把你的工作从开发主线上分离开来，以免影响开发主线
* 查看分支
  * git branch
* 查看所有分支（包含远程分支）
  * git branch -a 分支名

* 创建分支
  * git branch 新分支名
* 切换分支
  * git checkout 分支名
* 创建并切换到分支
  * git checkout -b 新分支名
* 合并分支
  * git merge 分支名
* 删除分支
  * git branch -d 分支名
* 强制删除分支
  * git branch -D 分支名
* 重命名分支
  * git branch -m “老分支名 新分支名”

## Git 分支-冲突

*  你在两个不同分支中，对同一个文件的同一个部分进行了不同的修改，Git不能干净的合并他们

## Git 远程仓库

* 远程仓库是指托管在英特网或其他网络中的你的项目的版本库
* 作用：本地仓库备份，多人协作
* 添加远程仓库
  * git remote add origin 远程仓库地址
* 推送到远程仓库
  * git push -u origin 分支名
* 拉取远程仓库
  * git pull
* 克隆远程仓库
  * git clone 远程仓库地址
* 删除远程仓库地址
  * git remote remove origin
* 配置SSH
  * ssh-keygen -t ed25519 -C ‘任意名字’
  * 生成的公钥放到远程仓库
