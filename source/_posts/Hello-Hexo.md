---
title: Hello Hexo
date: 2016-04-10 01:48:53
tags:
---
### 安装 git

```
sudo apt-get install git
```

配置git

```
git config --global user.name "yourname"
git config --global user.email "youremail"
```

配置ssh keys

- 备份自带key

```
cd ~/.ssh
mkdir key_backup
cp id_rsa* key_backup
rm id_rsa*
```

- 生成新的SSH Key：

```
$ ssh-keygen -t rsa -C "youremail"
```
按3个回车，密码为空。

- 添加SSH Key到GitHub：

复制id_rsa.pub内容
```
https://github.com/settings/ssh
```

- 检测

```
ssh -T git@github.com
```

### 安装hexo
```
sudo npm install hexo -g
sudo npm install hexo --save  #安装Hexo
hexo init blog  ＃下载模板
cd blog
sudo npm install #安装依赖
hexo server #启动服务
```
运行：http://localhost:4000/

### 部署到github
创建github repository: username.github.io
```
sudo npm install hexo-deployer-git --save #安装部署插件
```

- 编辑_config.yaml

```
deploy:
  type: git
  repository: https://github.com/username/username.github.io.git
  branch: master
```
```
hexo deploy #部署，https需要输入github账号密码，git模式需要ssh配置正确
```
### 开启hexo之旅吧！
