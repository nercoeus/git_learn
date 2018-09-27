1.CVS,SVN都是集中式版本控制系统,Git是分布式版本控制系统
集中式版本控制系统:
	版本库是集中存放在中央服务器的,要先从服务器上获得code到自己的电脑上才行.然后push到服务器上.
	需要联网工作
分布式版本控制系统:
	不需要联网,互相推送查看修改历程.安全系数极高.可以使用一台主机作为交换的桥梁
//git安装
sudo apt-get install git
//git设置本机属性,名称及email
git config --global user.name "~~~"
git config --global user.email "~~~"

//版本库的创建
git init

//为这个仓库添加README文件
git add README.txt

//提交文件到仓库,并加上说明
git commit -m "~~~"

//add和commit的区别,你可以先add多个文件,最后commit一次即可

//git status掌控当前仓库的状态
//git diff查看代码和仓库的不同

//使用git log查看版本管理
//每个版本均有commit编号

//调回上一个版本,更新本地仓库
git reset --hard HEAD^

//如果知道commit编号的话,也可以直接跳转
git reset --hard eg:2285f

//查看所有记录可以找到所有commit编号
git reflog

//add是将工作区文件提交到仓库的暂存区中,然后由commit提交至分支中,且提交后的暂存区被清空

//git跟踪管理的是修改而不是文件

//使用git checkout来丢弃工作区的修改,这里撤销后的状态先以暂存区为主,暂存区为空的话以版本库中为主
//这里的git checkout其实就是使用版本库里的来替换工作区中的文件,修改删除均可
//使用git rm file来删除版本库中的文件,然后commit即可
//使用git clone来进行仓库到本地代码库的获取,github有两种方式,自行选择

//git分支控制
git branch dev //创建dev分支
git checkout dev //切换分支

git branch //查看当前分支

Git鼓励大量使用分支：

查看分支：git branch

创建分支：git branch <name>

切换分支：git checkout <name>

创建+切换分支：git checkout -b <name>

合并某分支到当前分支：git merge <name>

删除分支：git branch -d <name>

//用git log --graph命令可以看到分支合并图

//使用git stash存储工作现场

//提交自己的code到仓库中,下面的remote命令,是记录远程仓库
//git remote add origin git@github.com:nercoeus/mini_yun.git

//使用git push origin master进行code提交,这里的master就是master分支,origin就是远程分支
