# CommonTools

### Git全局设置:
- git config --global user.name "erazhan"
- git config --global user.email "erazhan@163.com"


### git上传文件介绍
1. github上创建项目
2. 在想要操作的文件夹（或者桌面，但是后续要cd到该文件夹）中右键点击git bash here（如果没有则需要先安装Git）
3. 输入git init，会多一个.git隐藏文件夹
4. 输入git remote add origin https://github.com/erazhan/CommonTools.git(最后可根据具体仓库地址更改即可)
5. 输入git pull --rebase origin master,如果只是想要上传新的代码文件,则需要将原有的代码文件合并放到文件夹中
6. 输入git pull origin master，作用是将码云上的仓库pull到本地文件夹
7. 将需要上传的代码文件，复制粘贴到目标文件夹中
8. 输入git add .(上传所有文件)或者git add 文件名(上传单独的文件)
9. 输入git commit -m '文件描述,一般用first commit,init等都可以'
10. 输入git push origin master将本地仓库推送到远程仓库即可完成上传
- [参考网址](https://www.jianshu.com/p/3e0b213ab03d)

### github获取personal assess token
```angular2html
remote: Support for password authentication was removed on August 13, 2021.
remote: Please see https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls for information on currently recommended modes of authentication.
fatal: Authentication failed for 'https://github.com/erazhan/CommonTools.git/'
```
2021年8月13后，git上传更新项目文件时输入账号密码，不再用github的登录密码(password authentication)，改用个人token(personal assess tokens)。
- [官网教程](https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls)
- [申请个人token，包括mac修改钥匙串访问](https://blog.csdn.net/qq_32614525/article/details/121124216)
- [mac生成ssh key](https://blog.csdn.net/weixin_42164539/article/details/122992213)

### mac修改钥匙串访问
1. command+space输入并找到钥匙串访问。
2. 输入github.com,修改密码为申请的token, 如果没有直接新建一个, 名称填github.com,账号填自己的github的名称,密码填申请好的token。