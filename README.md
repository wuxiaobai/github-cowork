# github-cowork

利用 GitHub 进行协同工作的步骤说明

1. 为每一天的上手操作过程，创建一个单独的目录。

1. 每个目录下面创建若干个 Markdown 源码(*.md)文件。

1. 每个 Markdown 源码文件概要地介绍一项操作，比如：
  ```
  # 操作名称

  配置 samba 服务

  # 操作目的

  方便开发者在 Windows 操作系统中，借助资源管理器访问 Linux 虚拟机中的文件系统，就好像访问 Windows 下的一个盘符一样。

  # 操作步骤

  1. 借助管理员权限，安装 samba 服务： `sudo apt-get install samba`
    <br />
    注意事项：确保当前登录用户有 sudoer 的权限。

  1. 为 samba 服务创建用户名和密码：`smbpasswd -a username`
    <br />
    注意事项：samba 服务的 username 必须与当前登录用户的用户名一致，但密码可以与登录密码不同。

  ```

1. 尽量保证每个 Markdown 源码文件中介绍的操作相对独立，不要介绍重复了。
