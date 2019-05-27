git提交代码到GitHub时，由于多人同时对工程项目进行修改，可能会引起冲突，命令行会报一些错误。这里将我遇到的问题及解决方法记录下来。
## <font color="red">问题1：error：failed to push some refs to

**问题描述：**

命令行报 "error：failed to push some refs to ..." 错误？

报错截图如下：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190527185045730.png)

**解决方法1**

出现错误的主要原因是github中的README.md文件(已更新)不在本地代码目录中。
可通过git pull --rebase origin master命令进行代码合并， 这时候就可以在本地文件内看到README.md文件。之后再运行git push origin master命令进行推送。


**解决方法2**

使用git push -u origin master -f  命令强制提交。


## <font color="red">问题2：rebase in progress; onto adfced1

**问题描述**

运行git status命令查看状态时，提示rebase in progress; onto adfced1。。。。

报错截图：

![报错截图](https://img-blog.csdnimg.cn/20190527185628827.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3cxNDE4ODk5NTMy,size_16,color_FFFFFF,t_70)


**解决方法**

git的rebase命令提供了对历史提交进行修改的功能。
报错原因是之前或者刚刚用过 git rebase 命令，但上一次的进程还没有完成。
解决：查找哪里出现了冲突，你解决好conflicts之后，git add .，然后 git rebase --continue 就可以进入下一步。或者使用 git rebase --abort 来取消目前的进程。

如下：

![正常截图](https://img-blog.csdnimg.cn/20190527190950841.png)


## <font color="red">每天进步一点点、充实一点点、加油！！！