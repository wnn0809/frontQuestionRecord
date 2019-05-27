# web

## 本地项目如何上传到GitHub？

第一步：注册GitHub账号，已经有的情况下自动跳过这一步。如何注册GitHub账号可以自己百度

第二步：下载安装Git，通过百度，360软件商店都可以下载Git安装包。傻瓜式安装方法。

第三步： 登录GitHub，创建New repository，自己起个项目名称，勾选initialize this repository with a README。


第四步： 在本机电脑上找一位置存放远程库。如d盘。在空白处右击鼠标，点击Git Bash。
        输入'git clone 仓库地址'命令。如'git clone https://github.com/wnn0809/frontProjects.git'。 后面URL地址是在GitHub右侧点击'Clone or download'按钮输入框中复制过来的。


第五步： 第四步后会发现当前目录多出.git文件夹，如果没有显示查看文件夹属性将隐藏的文件打开。还有远程仓库文件夹。


第六步： 把自己的项目文件粘贴在第五步多出的远程仓库文件夹下，使用cd命令进入该文件夹。
        1.命令行输入 git add "上传文件的名称" 将文件添加到库。
        2.命令行输入 git commit -m"描述：如新增项目xxx".提交到本地的版本控制库里，引号里面是你对本次提交的说明信息
        3.命令行输入 git push -u origin master 将本地的仓库提交到你的github,最后会让输入github的账号和密码，输入回车之后再去看github项目，就看到本地项目出现在github上了。
		
		
问题解决：
1.如果遇到error：failed to push some refs to ...错误？

解决方法1：
通过以下命令进行代码合并
git pull --rebase origin master 这时候就可以在本地文件内看到README.md文件 之后再运行git push origin master`进行推送

解决方法2：
git push -u origin master -f   使用此命令强制提交