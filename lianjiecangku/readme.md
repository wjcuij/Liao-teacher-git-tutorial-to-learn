来到这一步折腾了几个小时，先说下不出错误的情况下正常步骤吧：

- 创建SSH Key。在用户主目录下C:\Users\Administrator，看看有没有.ssh目录，如果有，再看看这个目录下有没有id_rsa和id_rsa.pub这两个文件，如果已经有了，可直接跳到下一步。如果没有打开Shell（Windows下打开Git Bash），创建SSH Key：
$ ssh-keygen -t rsa -C "youremail@example.com"
- 登陆GitHub，打开“Account settings”，“SSH Keys”页面：然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容，另外一个是私钥
- 连接远程库
$ git remote add origin git@github.com:michaelliao/learngit.git
- 就可以把本地库的所有内容推送到远程库上：
$ git push -u origin master
- - （由于查看状态git status的时候总是有出现HEAD detached from 09d5a14，错误查不出所以就失败了）
- 贴个别人的方法吧：
![image](https://github.com/wjcuij/demo/blob/master/img/asd.png)

############################上面两个方法都不行于是我又换了另外一种方法############################
- 先克隆(前提是你在远程库里有这个库)learngit是远程库的名称
$ git clone https://github.com/wjcuij/learngit.git
Cloning into 'learngit'...
remote: Counting objects: 3, done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.
Checking connectivity... done.
- 然后进入那个文件随便添加一个文件
$ git add a.txt
$ git commit -m "add 1 file"
- 然后推上去
$ git push origin master
Fatal: AggregateException encountered.
Username for 'https://github.com': wjcuij
Counting objects: 3, done.
Delta compression using up to 2 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 284 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/wjcuij/learngit.git
   c2271a5..07cadad  master -> master

>>>上github查看库，成了！！！
