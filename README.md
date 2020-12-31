# How-to-push-folder-to-Github

# windows下提交文件夹到github

	https://blog.csdn.net/duxu24/article/details/70183503
	
	1. 在Github上new一个repository
	
	2. git init     # 在文件夹下建立git仓库
	
	3. git add .     #将所有文件添加到仓库
	
	4. git commit -m "smc code"     #提交到仓库
	
	5. git remote add origin https://github.com/WentaoWang-SH/SMC        #将本地仓库关联到github上 
	
	6. git push -u origin master         #上传代码到github远程仓库 此时需要输入用户名密码
	Username for 'https://github.com': shutom001@163.com
	Password:



# linux下提交文件夹到github
	https://blog.csdn.net/JiaXie15/article/details/107581243
	
	
	1. 在Github上new一个repository
	
	2. ubuntu下安装
	sudo apt-get install git
	
	3. ubuntu下：创建SSH Keys
	ssh-keygen -t rsa -C "18817392757@163.com"    
	一路回车下去
	创建好的加密文件在~/.ssh文件夹下，按住ctrl+h可以显示隐藏文件夹，点进去，打开id_rsa.pub，复制里面的key。
	
	
	4. GitHub上创建SSH keys
	到GitHub网站上添加SSH keys，进入Account Setting，左边点击”New SSH Key”，title随便填，粘贴key，点击Add SSH key。
	
	
	终端窗口输入如下命令，验证是否成功：
	ssh -T git@github.com
  
	如果看到如下信息，表示成功连上github 
	xj@xj-ThinkPad-T590:~/github_my$ ssh -T git@github.com
	Hi XieJia15! You've successfully authenticated, but GitHub does not provide shell access.
	
	5. 设置username和email
	git config --global user.name "wentao"
	git config --global user.email 18817392757@163.com
	
	
	6. 将本地文件夹提交大github远程仓库 (可参见windows下的操作步骤)
	#新建一个README.md文件，可以在里面编写文档
	echo"# exmple">>README.md
	 
	#新建并初始化仓库
	git init
	 
	#将文件夹内的所有文件都添加到仓库中，如果缺少哪个，可以使用 git add XXXX 添加；
	git add .
	#如果像我一样需要添加文件夹，输入
	git add /home/xj/UCB_pacman/search0103
	#后面为需要的文件夹路径
	 
	#上传文件至本地仓库， -m之后的输入是本次提交的说明。
	git commit -m "first commite"        
	
	#将本地文件夹和github仓库关联，后面是自己之前新建的github仓库地址
	git remote add origin git@github.com:XieJia15/UCB-pacman-AI-projects.git
	 
	#输入用户名和密码，输入正确，就可以成功将README.md上传到github上。
	git push origin master
	
	
