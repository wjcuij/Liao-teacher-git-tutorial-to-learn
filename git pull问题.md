### Git pull代码时候出现，或者push代码无效
> fatal: No remote repository specified.  Please, specify either a URL or a <br>
> remote name from which new revisions should be fetched. <br>

### 解决方法：
一、找到本地仓库项目里面的 .git文件夹，找到
config打开，修改里面内容为
> [plain] view plain copy <br>
> [core]   <br>
>         repositoryformatversion = 0   <br>
>         filemode = true   <br>
>         bare = false   <br>
>         logallrefupdates = true   <br>
>         ignorecase = true   <br>
>         precomposeunicode = false   <br>
> [remote "origin"]   <br>
>         url = https://github.com/CrossLee/xxx.git   <br>
>         fetch = +refs/heads/*:refs/remotes/origin/*   <br>
>         pushurl = https://github.com/CrossLee/xxx.git   <br>
> [branch "master"]   <br>
>         remote = origin  <br> 
>         merge = refs/heads/master   <br>

### 把其中换成你项目的地址就可以了：

> url = https://github.com/CrossLee/xxx.git <br>
> pushurl = https://github.com/CrossLee/xxx.git <br>

### 第二种方法查看你的路径是否与你git pull的路径或名字相同
