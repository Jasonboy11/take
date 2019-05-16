#GitHub和Git的初步使用

---

##一、注册GitHub

- 进入GitHub官网进行注册

---

##二、配置Git并获取密钥
- 1.下载安装Git
- 2.在你的目录文件夹中右键点击Git Bash Here
- ![](https://raw.githubusercontent.com/Jasonboy11/take/master/image/1.png)
- 3.配置Git的邮箱和密码：
<p>$ git config --global user.name "输入你的用户名"<p/>
<p>$ git config --global user.email "输入你的邮箱"<p/>
- 4.输入 $ssh-keygen -t rsa -C "your_email@youremail.com" 后面的your_email@youremail.com是你在github上注册使用的邮箱。
- 5.然后出现提示会要求确认路径密码，直接回车默认，它会显示秘钥图像代表keys已经生成了，我们需要这串秘钥来和GitHub上的远程仓库和本地仓库进行远程连接。
- ![](https://raw.githubusercontent.com/Jasonboy11/take/master/image/2.png)
- 6.找到秘钥路径C:\Users\Jason\.ssh里面的id_rsa.pub文件，右键记事本打开，复制全部keys。
- ![](https://raw.githubusercontent.com/Jasonboy11/take/master/image/3.png)

---

##三、在GitHub中添加密钥
- 1.右上角点击自己的头像，再点设置，找到SSH和GPG密钥，再点击新的SSH秘钥，进图添加界面，创建一个标提，然后再把刚刚复制的的密钥粘贴到键中，最后点击添加SSH密钥。
- ![](https://raw.githubusercontent.com/Jasonboy11/take/master/image/4.png)
- ![](https://raw.githubusercontent.com/Jasonboy11/take/master/image/5.png)
- 2.验证链接是否成功打开Git Bash,输入命令 $ ssh -T git@github.com，第一次输入会显示continue？，输入yes继续，看到显示You've successfully authenticated, but GitHub does not provide shell access代表连接已经成功。


---

##四、Git编辑本地仓库和上传到GitHub远程仓库
- 1.初始化仓库，这一步很重要，如果没有初始化过的仓库将无法执行任何操作，检查是否已经初始化可以在当前文件夹查看有没有.git文件夹（注意是隐藏文件，需要在文件夹选项中勾选查看隐藏项目）如果没有就输入 $ git init
- 2.添加你的项目文件，一般GitHub默认有一个README文件，即说明文件，把他看做一个文本文件，用来说明描述项目或有关说明。我们首先创建它，输入$ echo "#测试说明" >> README.md
- 3.用git add添加文件进入git版本库，在此之前先输入$ git status来查看文件变动，看见标红的README.md文件说明此文件有新改动但是没有上传保存。我们将它添加进去，输入$ git add README.md 添加文件，再提交备注信息，输入$ git commit -m "你的备注信息"
- ![](https://raw.githubusercontent.com/Jasonboy11/take/master/image/7.png)
- ![](https://raw.githubusercontent.com/Jasonboy11/take/master/image/8.png)
- 4.把文件push到GitHub里，在你的GitHub上新建项目库（点击右上角头像左边的＋号，点击新存储库）,然后在数据库名称里自己起一个你的远程仓库名，其他默认，点击创建
- ![](https://raw.githubusercontent.com/Jasonboy11/take/master/image/6.png)
- 5.在创建好的项目库中提示添加你的项目文件，我们的项目文件在本地，所以选择第一种，复制它的SSH
- ![](https://raw.githubusercontent.com/Jasonboy11/take/master/image/9.png)
- 6.回到你的本地项目文件夹，绑定远程仓库，只需要在gitbash中输入$ git remote add origin "粘贴第5步复制的SSH地址"(右键paste)，然后敲回车。没有报错就接着输入$ git push -u origin master ，回车之后等待一段时间，可以看到文件上传成功，回到GitHub仓库下刷新，如果能显示刚刚添加README文件则证明已经上传成功
- ![](https://raw.githubusercontent.com/Jasonboy11/take/master/image/10.png)

---

##五、6个常用命令
- 1.$ git init -->初始化本地仓库（每个项目文件夹下只需要初始化一次即可）
- 2.$ git status -->查看状态
- 3.$ git add 文件名-->跟踪修改文件（更新文件）
- 4.$ git commit -m "你的备注信息"-->提交所有更新过的文件
- 5.$ git remote add origin github的SSH地址.git-->添加远程版本库
- 6.$ git push -u origin master-->上传代码及快速合并
- 常用命令表：
- ![](https://raw.githubusercontent.com/Jasonboy11/take/master/image/git.jpg)


