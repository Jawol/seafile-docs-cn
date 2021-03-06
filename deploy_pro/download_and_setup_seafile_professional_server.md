- [准备工作](#wiki-preparation)
- [下载与安装](#wiki-download-and-setup)
- [安装完成](#wiki-done)

## <a id="wiki-preparation"></a>准备工作 ##

### 系统最低配置需求 ###

- 一台至少 2GB 内存的 Linux 服务器

### 安装 Java 运行时环境 (JRE) ###

如果您的系统环境是 Ubuntu 或者 Debian，执行以下命令：
```
sudo apt-get install default-jre
```

如果您的系统环境是 CentOS 或者 Red Hat，执行以下命令：
```
sudo yum install java-1.6.0-openjdk
```

*注意*： 您既可以使用 openJDK JRE 也可以使用 Oracle JRE，但是不要使用 GCJ(GNU Java) 包。

### 安装 poppler-utils ###

poppler-utils 提供对 PDF 文件的全文检索功能。

如果您的系统环境是 Ubuntu 或者 Debian，请执行以下命令：
```
sudo apt-get install poppler-utils
```

如果您的系统环境是 CentOS 或者 Red Hat，请执行以下命令：
```
sudo yum install poppler-utils
```


### 安装 Libreoffice 和 UNO 库 ###

Libreoffice 和 Python-uno 库为 office 文件提供在线预览功能。如果它们没有安装，office 文件就不能在线预览。

**注意**：我们推荐 libreoffice 4.0 或者以后的版本，老版本的 libreoffice 不能正确地处理非英文字符



如果您的系统环境是 Ubuntu 或者 Debian，执行以下命令：
```
sudo apt-get install libreoffice python-uno
```

如果您的系统环境是 CentOS 或者 RHEL，执行以下命令：
```
sudo yum install libreoffice libreoffice-headless libreoffice-pyuno
```

对于其他的 Linux 发行版您可以参考：[Linux 系统下安装 LibreOffice](http://www.libreoffice.org/get-help/installation/linux/)

一般地，您还需要为您的使用语言安装字体，特别是在亚洲地区，否则 office 文件和 pdf 文件不能正确地显示。 

比如， 中国的用户可能希望安装文泉驿系列的 TrueType 字体：

```
# 如果您的系统环境是 Ubuntu 或者 Debian，执行以下命令：
sudo apt-get install ttf-wqy-microhei ttf-wqy-zenhei xfonts-wqy
```


### 安装 Python 库 ###

首先确保您已经安装了 python 2.6 或者 2.7 版本
```
sudo easy_install pip
sudo pip install boto
```

在安装过程中如果您遇到错误："Wheel installs require setuptools >= ..."， 请在以上两条命令之间运行以下命令：
```
sudo pip install setuptools --no-use-wheel --upgrade
```

## <a id="wiki-download-and-setup"></a>下载与安装 Seafile 专业版服务器 ##

### 获得许可证书 ###

将您得到的许可证书放在顶层目录下。比如，在这篇文档页面里，我们把 `/data/haiwen/` 作为顶层目录。


### <a id="wiki-download-and-uncompress"></a>下载与解压 Seafile 专业版服务器 ###

- 32 位
- [64 位](https://cloud.seafile.com/repo/4cbf838a-bbb7-4106-a6b5-27f6d382dc90/)

```
tar xf seafile-pro-server_2.1.5_x86-64.tar.gz
```

现在您的目录结构应该像如下这样：

```
haiwen
├── seafile-license.txt
└── seafile-pro-server-2.1.5/
```


-----------

您应该已经注意到社区版服务器和专业版服务器名字的不同。以 64 位的 2.1.5 版本为例：

- Seafile 社区版服务器压缩包叫作 `seafile-server_2.1.5_x86-86.tar.gz`；解压后，文件夹名叫作  `seafile-server-2.1.5`
- Seafile 专业版服务器压缩包叫作 `seafile-pro-server_2.1.5_x86-86.tar.gz`；解压后，文件夹名叫作 `seafile-pro-server-2.1.5`
    
-----------


### 安装 ###

Seafile 专业版服务器的安装步骤与Seafile 社区版服务器安装步骤相同。请参考社区维基：[下载与安装 Seafile 服务器并使用 MySQL 数据库](https://github.com/haiwen/seafile/wiki/Download-and-Setup-Seafile-Server-with-MySQL)

在您成功安装 Seafile 专业版服务器之后，您的目录结构应该像如下这样：

```
#tree haiwen -L 2
haiwen
├── seafile-license.txt # license file
├── ccnet               # configuration files
│   ├── ccnet.conf
│   ├── mykey.peer
│   ├── PeerMgr
│   └── seafile.ini
├── pro-data            # data specific for professional version
│   └── seafevents.conf
├── seafile-data        
│   └── seafile.conf
├── seafile-pro-server-2.1.5
│   ├── reset-admin.sh
│   ├── runtime
│   ├── seafile
│   ├── seafile.sh
│   ├── seahub
│   ├── seahub-extra
│   ├── seahub.sh
│   ├── setup-seafile.sh
│   ├── setup-seafile-mysql.py
│   ├── setup-seafile-mysql.sh
│   └── upgrade
├── seahub-data
│   └── avatars         # for user avatars
├── seahub.db
├── seahub_settings.py   # seahub config file
```

## <a id="wiki-done"></a>安装完成

到此，Seafile 专业版服务器的基本安装已经完成。 

您可能想要了解更多关于 Seafile 专业版服务器的信息：

- [[安装 Seafile 专业版服务器并使用亚马逊 S3]]
- [[Seafile 专业版服务器的 FAQ]]
