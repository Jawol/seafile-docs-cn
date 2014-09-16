# FAQ

#### 当下载一个库，客户端显示"connecting server"

首先检查ccnet.log客户端登录日志   (``~/.ccnet/logs/ccnet.log`` for
Linux, ``C:/users/your_name/ccnet/logs/ccnet.log`` for Windows) 看看有没有报错信息.

可能导致的错误:

* Miss config of  <code>SERVICE_URL</code>: Check whether the value of is set correctly in server's <code>ccnet.conf</code>.
* 防火墙: 确认防火墙允许Seafile服务端口，如果阻止请配置允许.

Trouble shooting:

* 用 telnet 试试能否正常连接: <code>telnet your-server-IP-or-domain 10001</code>

#### Failed to upload/download file online

* Make sure you firewall for seafile fileserver is opened.
* Using chrome/firefox debug mode to find which link is given when click download button and what's wrong with this link

#### Does Seafile server support Python 3?

No, You must have python 2.6 or 2.7 installed on your server.

#### Can Seafile server run on FreeBSD?

There was an unconfirmed solution on the internet, which later has vanished.
(Please explain the installation routine if you successfully set up Seafile in FreeBSD.)

#### Website displays "Page unavailable", what can I do?

* You can check the back trace in seahub log files('''installation folder/logs/seahub_django_request.log''')

* You can also turn on debug by adding <code>DEBUG = True</code> to seahub_settings.py and restart seahub by <code>./seahub.sh restart</code>, then refresh that page, all the debug infomations will be displayed. Make sure ./seahub.sh was started as: ./seahub.sh start-fastcgi

#### Avatar pictures vanished after upgrading server, what can I do?

* You need to check whether the "avatars" symbolic link under seahub/media/ is correctly link to ../../../seahub-data/avatars. If not, you need to correct the link according to the "minor upgrade" section in [[Upgrading-Seafile-Server]]

* If your avatars link is correctly linked, and avatars are still broken, you may refresh seahub cache by <code>rm -rf /tmp/seahub_cache/*</code>

#### How to change seafile-data location after setup?

Modify file seafile.ini under ccnet. This file contains the location of seafile-data. Move seafile-data to another place, like `/opt/new/seafile-data`. Then modify the file accordingly.

#### Failed to send email, what can I do?

Please check logs/seahub.log.

There are some common mistakes:

1. Check whether there are some typos in the config, e.g., forget single quote, EMAIL_HOST_USER = XXX, which should be EMAIL_HOST_USER = 'XXX'
1. Your mail server is not available.

