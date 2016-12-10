git基本操作步骤：
开始之前请配置git用户信息：
git config --global user.name "Your Name"
git config --global user.email "email@example.com"

１．ｇｉｔ初始化
1）git remote：
git clone git@github.com:aaronkingdom/projects.git # 从远程仓库复制一份到本地
git remote add origin git@github.com:aaronkingdom/projects.git	＃　添加远程仓库
2）git init：
git init	#　初始化

２．基本操作
git add xxx	＃　添加ｘｘｘ到交换缓存区
git commit  -m "xxxx"	＃　提交到版本库，并添加描述
git status	#　查看状态 
git checkout -- xxx	# 删除ｘｘｘ文件
git log 	# 查看log

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

git tag <tagname>	# 创建标签
git tag	＃　显示标签名
get show <tagname>	＃　显示标签内容
git push origin <tagname>	＃创建远程标签


３．添加证书
登陆GitHub，打开“Account settings”，“SSH Keys”页面：
然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容
ssh-keygen -t rsa -C "youremail@example.com"	＃　创建证书

4.提交到远程仓库
git remote add origin git@github.com:aaronkingdom/projects.git	＃　关联远程仓库
git pull　＃　从远程抓取分支
git push -u origin master　＃　推送到远程仓库

