# GitTutorial

### Git全局设置:
- git config --global user.name "erazhan"
- git config --global user.email "erazhan@email.com"


### git上传文件介绍
1. github上创建项目
2. 在想要操作的文件夹（或者桌面，但是后续要cd到该文件夹）中右键点击git bash here（如果没有则需要先安装Git）
3. 输入git init，会多一个.git隐藏文件夹
4. 输入git remote add origin https://github.com/erazhan/GitTutorial.git (最后可根据具体仓库地址更改即可)
5. 输入git pull --rebase origin master,如果只是想要上传新的代码文件,则需要将原有的代码文件合并放到文件夹中
6. 输入git pull origin master，作用是将github上的仓库pull到本地文件夹
7. 将需要上传的代码文件，复制粘贴到目标文件夹中
8. 输入git add .(上传所有文件)或者git add 文件名(上传单独的文件)
9. 输入git commit -m '文件描述,一般用first commit,init等都可以'
10. 输入git push origin master将本地仓库推送到远程仓库即可完成上传
11. git branch release/0.0.1创建分支
12. git checkout release/0.0.1切换分支，或者git checkout -b release/0.0.1直接创建分支并切换
13. git tag v0.0.1, 创建本地tag
14. git push origin v0.0.1, 推送到远程仓库

- [参考网址](https://www.jianshu.com/p/3e0b213ab03d)
- [git branch介绍](https://www.jianshu.com/p/9186369d577a)
- [git branch使用](https://blog.csdn.net/weixin_43404836/article/details/108995478)
- [git tag介绍](https://blog.csdn.net/CSDN_KONGlX/article/details/125484338)

### 备注
- .gitignore最好在上传文件前进行创建，否则不会忽略已经上传过的文件
- .git文件保存了当前所有信息

### github获取personal assess token
```angular2html
remote: Support for password authentication was removed on August 13, 2021.
remote: Please see https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls for information on currently recommended modes of authentication.
fatal: Authentication failed for 'https://github.com/erazhan/CommonTools.git/'
```
2021年8月13后，git上传更新项目文件时输入账号密码，不再用github的登录密码(password authentication)，改用个人token(personal assess tokens)。
- [官网教程](https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls)
- [申请个人token，在mac上修改钥匙串访问](https://blog.csdn.net/qq_32614525/article/details/121124216)
  - 首先登录github，找到[settings](https://github.com/settings)，并在Developer Settings中的Personal access tokens找到[Tokens(classic)](https://github.com/settings/tokens)
  - 然后点击Generate new tokens，Note随意填个相关内容，Expiration填No expiration，Select scopes尽量全选，完成后复制新建的token（最好保存起来）
  - 然后在mac上打开钥匙串访问（command+space或者点击mac右上角的搜索输入钥匙串访问），搜索github.com，如果没有则新增一个，url地址填https://github.com，用户/账户填github绑定的邮箱名称，密码填入上一步复制的token
- 另外在mac上[生成ssh key](https://blog.csdn.net/weixin_42164539/article/details/122992213)，然后添加到github中
  - 首先```cd ~/.ssh```，如果[没有~/.ssh文件夹](https://blog.csdn.net/zjc910997316/article/details/128094736)，执行```ssh localhost```或者直接执行```ssh```就会在```～/```目录下生成这个文件
  - 然后执行```ssh-keygen -t rsa -C "erazhan@email.com"```，邮箱和github绑定的邮箱保持一致，然后一路默认点enter
  - ```cat id_rsa.pub```或者```vim id_rsa.pub```，复制中的key，包含开头ssh-rsa（这个在下一步复制到github中时也会有要求的格式）
  - 登录github，找到[settings](https://github.com/settings)中的[ssh](https://github.com/settings/keys)，点击New SSH key按钮将自己的key复制保存即可
  
