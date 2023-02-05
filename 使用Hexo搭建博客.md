# 前言
    该笔记是记录使用Hexo搭建博客的笔记

    使用Hexo需要的工具：
        node.js     git     hexo    github账号(利用github作为服务器)

    hexo下载命令行
        npm install hexo-cli -g   # 全局安装hexo
    查询版本命令行
        node -v
        git -v
        hexo -v

# 步骤
    1、github建立一个仓库，命名为  github账户名称.github.io
        Add a README file
        
    2、生成SSH key
        进入一个文件夹中右键使用 git bush here

        在git bush 中输入命令行
            ssh  # 检查有无安装ssh，在安装git时默认是安装的

        生成ssh
            ssh-keygen-t rsa -C "邮箱地址"  # 邮箱地址为注册github时的邮箱地址
            按四次回车键（在本地c盘的用户文件夹中生成一个.ssh文件夹）
        
        打开ssh文件夹
            打开id_rsa.pub(用notepad++)，全选复制内容（ctrl + a; ctrl + c）

        回到github
            在个人头像下方点击 Settings
            点击左侧的SSH and GPG keys -> SSH keys

            title自己命名
            将刚刚复制的notepad++的代码 粘贴到key里面，点击Add SSH key
        
        回到git bush here
            测试ssh是否绑定成功
            ssh -T git@github.com
    
    3、 本地生成博客内容
        在想要的目录下新建一个文件夹，进入后使用git bush here打开
        hexo init   # 初始化hexo博客，把hexo框架从github拷贝下来
        hexo g  # 生成
        hexo s  # 启动服务

    4、 发布博客到互联网
        打开刚刚新建的文件夹，里面已经多了一些文件，打开_config.yml（notepad++）

        修改内容：
            deploy:
                type: git
                repository: https://github.com/hanbing1307/hanbing1307.github.io.git
                branch: main

            在ssh文件下用git bush here 打开命令行
                安装hexo-deployer-git自动部署发布工具：
                    npm install hexo-deployer-git --save
                    Hexo g 生成页面
                    Hexo d 上传

                    回到github页面，查看仓库情况，仓库左上角为访问的地址



    

