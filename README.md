来源：http://huangshanben.com/articles/3080/

一、git基本操作步骤：
开始之前请配置git用户信息：
git config --global user.name "Your Name"
git config --global user.email "email@example.com"

１．ｇｉｔ初始化
git clone git@github.com:aaronkingdom/projects.git # 从远程仓库复制一份到本地
git remote add origin git@github.com:aaronkingdom/projects.git＃　关联远程仓库
或者
git init    #　初始化

２．基本操作
git add xxx＃　添加ｘｘｘ到交换缓存区
git commit  -m "xxxx"＃　提交到版本库，并添加描述
git status#　查看状态 
git checkout -- xxx# 删除ｘｘｘ文件
git log # 查看log

删除文件
rm xxx
git rm
git commit
或者
git checkout -- ｘｘｘ

添加分支
git branch xxx
git checkout xxx # 切换到分支
或者
git checkout -b xxx
git merge aaa　＃　合并aaa到当前分支

查看分支
git branch# 查看本地分支
git branch -r# 查看远程分支

git tag <tagname># 创建标签
git tag＃　显示标签名
get show <tagname>＃　显示标签内容
git push origin <tagname>＃创建远程标签

３．添加证书
登陆GitHub，打开“Account settings”，“SSH Keys”页面：
然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容
ssh-keygen -t rsa -C "youremail@example.com"＃　创建证书

4.提交到远程仓库
git remote add origin git@github.com:aaronkingdom/projects.git＃　关联远程仓库
git pull　＃　从远程抓取分支
git push -u origin master　＃　推送到远程仓库
git push origin test:master         // 提交本地test分支作为远程的master分支


二、 Git 常用命令
1) 远程仓库相关命令
git clone git://github.com/jQuery/jquery.git    # 检出仓库
git remote -v    # 查看远程仓库
git remote add [name] [url]    # 添加远程仓库
git remote rm [name]    # 删除远程仓库
git remote set-url --push [name] [newUrl]    # 修改远程仓库
git pull [remoteName] [localBranchName]    # 拉取远程仓库
git push [remoteName] [localBranchName]    # 推送远程仓库
*如果想把本地的某个分支test提交到远程仓库，并作为远程仓库的master分支，或者作为另外一个名叫test的分支，如下：
git push origin test:master         // 提交本地test分支作为远程的master分支
git push origin test:test              // 提交本地test分支作为远程的test分支

2）分支(branch)操作相关命令
git branch    # 查看本地分支
git branch -r    # 查看远程分支
git branch [name]     # 创建本地分支----注意新分支创建后不会自动切换为当前分支
git checkout [name]    # 切换分支
git checkout -b [name]    # 创建新分支并立即切换到新分支
git branch -d [name]     # 删除分支---- -d选项只能删除已经参与了合并的分支，对于未有合并的分支是无法删除的。如果想强制删除一个分支，可以使用-D选项
git merge [name]    # 合并分支 ----将名称为[name]的分支与当前分支合并
git push origin [name]    # 创建远程分支(本地分支push到远程)
git push origin :heads/[name] 或 $ gitpush origin :[name]     # 删除远程分支
*创建空的分支：(执行命令之前记得先提交你当前分支的修改，否则会被强制删干净没得后悔)
git symbolic-ref HEAD refs/heads/[name]
rm .git/index
git clean -fdx

3）版本(tag)操作相关命令
git tag    # 查看版本
git tag [name]    # 创建版本
git tag -d [name]    # 删除版本
git tag -r    # 查看远程版本
git push origin [name]    # 创建远程版本(本地版本push到远程)
git push origin :refs/tags/[name]    # 删除远程版本
git pull origin --tags    # 合并远程仓库的tag到本地
git push origin --tags    # 上传本地tag到远程仓库
git tag -a [name] -m 'yourMessage'    # 创建带注释的tag
