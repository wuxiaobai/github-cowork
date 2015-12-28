# 操作名称

获取 Linux 虚拟机导出文件

# 操作目的
获取 Linux 虚拟机导出文件,可以在windows下对文件进行编辑
TODO

# 操作步骤
## 步骤一

借助管理权限编辑 sudoers 文件

```
vi /etc/sudoers
```

为用户 wudi 增加 sudo 运行权限，

```
wudi	ALL=(ALL:ALL) ALL
```

利用同样的方法，也可以为其他用户增加 sudo 运行权限。

编辑完毕后请保存 sudoer 文件。

## 步骤二

利用 smbpasswd 命令创建 samba 账户。此账户将被用于从 Windows 资源管理器访问 Linux 下的目录和文件。

```
sudo smbpasswd -a username
```
## 步骤三

修改 sudo vi /etc/samba/smb.conf ，这里 username 需要被替换为用 smbpasswd 命令创建的账户，而不是 Linux 账户。

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

## 步骤四

重启 samba 服务器

```
sudo /etc/init.d/samba restart
```

## 步骤五

如果在 Windows 上曾经以某个用户名 user1 访问过 samba 服务器，再想使用 user2 访问 samba 服务器时，会出现无法访问的错误，这时候可以在 Windows 的 cmd 命令行界面下使用这个命令消除冲突：

```
net use * /del

看到提示信息后，直接按 Y 键确认
```