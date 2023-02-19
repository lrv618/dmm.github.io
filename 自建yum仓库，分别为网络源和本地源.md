# 自建yum仓库，分别为网络源和本地源

mestryas 2018-07-22 22:14:38  1104  收藏 1
版权
所有Yum仓库的配置文件均需以 .repo 结尾并存放在/etc/yum.repos.d/目录中的

[rhel-media] : yum仓库唯一标识符，避免与其他仓库冲突。

name=linuxprobe : yum仓库的名称描述，易于识别仓库用处。

baseurl=file:///media/cdrom :提供方式包括FTP（ftp://..）、HTTP（http://..）、本地（file:///..）

enabled=1 : 设置此源是否可用，1为可用，0为禁用。

gpgcheck=1 : 设置此源是否校验文件，1为校验，0为不校验。

gpgkey=file:///media/cdrom/RPM-GPG-KEY-redhat-release :若为校验请指定公钥文件地址。

 

配置网络源

1.查看网络源配置文件，如果将yum 网络源配置文件改名为CentOS-Base.repo.bak，会先在网络源中寻找适合的包，改名之后直接从本地源读取

[root@localhost ~]# cd /etc/yum.repos.d/
[root@localhost yum.repos.d]# ls
CentOS-Base.repo.bak  CentOS-Debuginfo.repo  CentOS-local.repo  CentOS-Sources.repo
CentOS-CR.repo        CentOS-fasttrack.repo  CentOS-Media.repo  CentOS-Vault.repo
[root@localhost yum.repos.d]# mv CentOS-Base.repo.bak CentOS-Base.repo
[root@localhost yum.repos.d]# ls
CentOS-Base.repo  CentOS-Debuginfo.repo  CentOS-local.repo  CentOS-Sources.repo
CentOS-CR.repo    CentOS-fasttrack.repo  CentOS-Media.repo  CentOS-Vault.repo


2. 创建配置文件

[root@localhost yum.repos.d]# vim CentOS-Base.repo.bak

[bash]
name=Base Repo
baseurl=https://mirrors.aliyun.com/centos/7.4.1708/os/x86_64/
gpgcheck=0
enabled=1

[epel]
name=epel 7 Release 7
baseurl=https://mirrors.aliyun.com/epel/7/x86_64/
gpgcheck=0
enabled=1

[root@localhost yum.repos.d]# yum repolist

yum makecache作用：就是把服务器的包信息下载到本地电脑缓存起来，makecache建立一个缓存，以后用install时就在缓存中搜索，提高了速度

Loaded plugins: fastestmirror
Loading mirror speeds from cached hostfile

* base: mirrors.aliyun.com
* epel: mirrors.aliyun.com
repo id                                             repo name                                                status
Base                                               Base Repo
epel                                               epel 7 Release 7

————————————————



### 挂载本地yum源

如果想加快安装速度（yum源指向本地光盘）：

 [root@ServerB ~]# mount /dev/cdrom /mnt

  [root@ServerB ~]# mkdir /bk

[root@ServerB ~]#cd /etc/yum.repos.d/

[root@ServerB ~]# mv /etc/yum.repos.d/*  /bk/

[root@ServerB ~]# vim /etc/yum.repos.d/a.repo

[base]

name=base

baseurl=file:///mnt/BaseOS

enabled=1

gpgcheck=0

 

[app]

name=app

baseurl=file:///mnt/AppStream

enabled=1

gpgcheck=0

[root@ServerB ~]# yum groupinstall "Server with GUI"

[root@ServerB ~]#partx



cat /etc/fstab

/dev/cdrom	/mnt		swap		defaults	0 0

mount  -a
