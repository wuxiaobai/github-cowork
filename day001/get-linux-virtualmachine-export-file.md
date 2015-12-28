# 操作名称

获取 Linux 虚拟机导出文件

# 操作目的

获取linux虚拟机的导出文件

# 操作步骤

1.新建一个目录
2.修改.sudo vi /etc/samba/smb.conf 
3.sudo smbpasswd -a username修改用户名密码
4.sudo /etc/init.d/samba restart重新启动
