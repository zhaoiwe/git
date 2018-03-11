## git命令
 * 在gitbash上使用mkdir创建一个文件，把需要的代码复制到这个目录上面
 * 初始化一个Git仓库文件，使用git init命令,把文件交给git管理
 * 添加文件到Git仓库，分两步：第一步，使用命令git add <file>提交到本地版本库的暂存区，注意，可反复多次使用，添加多个文件；第二步，使用命令git commit -m "提交修改说明"把暂存区的东西提交到本地仓库的当前分支master中，如果文件修改错乱可以从最近的一个commit提交恢复，多次修改的文件提交到暂存区，再一次提交到分支中
 * git status 查看仓库的状态
 * git diff 查看对仓库做了说明修改，如果git status告诉你有文件被修改过，用git diff可以查看修改内容。
 * git log命令显示从最近到最远的提交日志
 * 在Git中，用HEAD表示当前版本，上一个版本就是HEAD^，上上一个版本就是HEAD^^依次类推
 * 我们要把当前版本回退到上一个版本，使用git reset命令：git reset --hard HEAD^，使用git reset commit id版本号可以回到对应的版本当你用$ git reset --hard HEAD^回退到上一个版本时，再想恢复到回退之前的版本，就必须找到就必须找到回退前的版本id即commit id。Git提供了一个命令git reflog用来记录你的每一次命令，找到版本id使用git reset --hard 4442334就可以回退到id对应的版本
 * git checkout从版本库更新文件到工作区
 * 把本地库的内容推送到远程，用git push命令，实际上是把当前分支master推送到远程,git push -u origin master，第一次推送master分支的所有内容，之后使用git push origin master
 * 远程库备好，使用命令git clone克隆一个本地库：$ git clone git@github.com:xxx/xxx.git
 * git checkout命令加上-b参数表示创建并切换分支相当于2条命令：$ git branch xxx
   $ git checkout xxx
 * git branch命令查看当前分支
 * git merge命令用于合并指定分支到当前分支
 * $ git checkout master 切换回master分支
 * 
 * 
 
##git的概念
 **Git和其他版本控制系统如SVN的一个不同之处就是有暂存区的概念**

 * git的工作区就是一个目录（Working Directory）
 * 版本库（Repository）工作区有一个隐藏目录.就是是Git的版本库。Git的版本库里其中最重要的就是称为stage（或者叫index）的暂存区，还有Git为我们自动创建的第一个分支master，以及指向master的一个指针叫HEAD。
 * 工作区——————》add————》stage暂存区----->commit------master分支（stage暂存区+master=版本库）
##Git仓库和GitHub仓库之间的传输
* 第1步：创建SSH Key。在用户主目录下，看看有没有.ssh目录，如果有，再看看这个目录下有没有id_rsa和id_rsa.pub这两个文件，如果已经有了，可直接跳到下一步。如果没有，打开Shell（Windows下打开Git Bash），创建SSH Key：
>$ ssh-keygen -t rsa -C "youremail@example.com"
>$ git remote add origin git@github.com:xxx/xxx.git本地仓库和远程github关联命令
* Git支持多种协议，包括https，但通过ssh支持的原生git协议速度最快。
