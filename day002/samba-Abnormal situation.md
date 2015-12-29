#操作名称

samba的安装的配置

#操作目的

samba的安装的配置

#操作内容

1.借助管理权限编辑 sudoers 文件

```
vi /etc/sudoers
```

2、为用户 wudi 增加 sudo 运行权限，

```
shenh	ALL=(ALL:ALL) ALL
```

3、利用 smbpasswd 命令创建 samba 账户。此账户将被用于从 Windows 资源管理器访问 Linux 下的目录和文件。

```
sudo smbpasswd -a username
```

4、修改 sudo vi /etc/samba/smb.conf ，这里 username 需要被替换为用 smbpasswd 命令创建的账户，而不是 Linux 账户。

```
[username]
  comment = username's smb dir
  path = /home/username/somedir
  valid users = username
  public = no
  writable = yes
  read only = no
  printable = no
  create mask = 0777
```

5、重启 samba 服务器

```
sudo /etc/init.d/samba restart
```
