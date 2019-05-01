# git笔记  

## 一、安装&配置  

### **1.安装**  

安装时：Use git from git bash only... 其他默认下一步  

-------------

### **2.配置**

配置path： D:\\..\git\bin  

配置git: 用户名和邮箱   
 
+ 右键-git bash
+ `git config --global user.name "name"`    
+ `git config --global user.email "xxx@xxx.xxx"`  

查看用户名密码  

+ C:\User\***\.gitconfig

----------

搭建git服务器（远程仓库）： [github.com](https://github.com "github")  
 
-----------


# 二、**ssh:本地-远程**  

为了在本地和远程仓库之间进行 免密钥登录，可以配置ssh 

+  配置ssh：先在本地配置，发送给远程

+  现在本地生成ssh：
 `ssh-keygen -t rsa -C xxx@qq.com`   一直回车  直到出现字符图画
+ 发送给远程：  

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;***github里 - settings - SSH and ... - New SSH  - title任意、key中输入*** 
  
+ 刚才在本地生成的ssh：  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;将本地刚才生成的ssh内容复制到远程的Key中:`C:/xxx/.ssh/id_rsa.pub`

+ 测试连通性：`ssh -T git@github.com`->`yes`

如果本地和远程成功通信，则可以在 /.ssh目录中 发现known_hosts文件  

如果失败：多尝试几次 、检查回车符(粘贴之后会多一个回车符)  

##### 在本地新建git项目
在项目根目录  右键 - git bash ->`git init`

##### 在远程建立git项目  
your projects -> Repositories -> new    
Clone or download->`https://github.com/xxx/xxxx.git`

# **三、本地项目-远程项目关联**  

`git remote add origin https://github.com/xxx/xxxx.git`

## 第一次发布项目 （本地-远程）
+ `git add .` &nbsp;&nbsp;&nbsp;&nbsp; //文件-暂存区  
+ `git commit -m "注释内容"` &nbsp;&nbsp;&nbsp;&nbsp; //暂存区-本地分支（默认master）  
+ `git push -u origin master`


## 第一次下载项目（远程-本地）
`git clone git@github.com:yanqun/mygitremote.git`

## 提交(本地-远程)
(在当前工作目录 右键-git bash)
`git add.`
`git commit -m "提交到分支"`
`git push  origin master`

## 更新(远程-本地)
`git pull`


# Egit：在Eclipse中操作git
目前的eclipse基本都支持git，如果不支持 则到eclplise marktplace 搜git安装

## 配置：

+　a.team-git-configuration -邮箱 用户名  
+　b.general -network -ssh2选中 生成的ssh目录  　

## **第一次发布**

+ share project

+ 加入暂存区add to index

+ 提交到本地分支commit 

+ 将项目推送到远程	  右键-team -remote -push ---


## **提交**  

+ team-add to index  

+ team -commit  

+ team -push  


## **commit时：**  

+ commit and push 或commit按钮的区别：  

+ commit按钮：不能单独的Push某一个文件，只能Push整个项目  

+ commit and push：可以 单独Push某一个文件  


## **第一次下载**
import -clone -输入 https/ssh的唯一标示符


## **更新**
team - remote -pull


## **git冲突的解决：**
发现冲突：	进入同步视图  右键——team - synchronized...  

**解决：**  
+ 添加到本地暂存区 add to index  

+ 提交到本地分支 commit  

+ 更新服务端的分支内容  到本地分支 pull  

+ 修改冲突：直接修改 或者 merge tool  

	已经变为了普通本地文件  

	add to index  

	commit push  

------------
# git多个人 团队协作开发

github中 该项目 -settings

增加合作者： Collaborators 加入 合作者：github 全名或邮箱

发送邀请链接


合作伙伴： 打开该链接、接受邀请 :合作开发....clone项目、修改、add \commit\push


