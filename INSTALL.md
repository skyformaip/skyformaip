# SkyForm AIP快速安装指南

## 准备

SkyForm AIP安装需要：

1.  hosts文件，包含AIP集群所有节点的IP地址和节点名，格式与系统/etc/hosts一样，例子：

```
192.168.20.100 exp001  
192.168.20.101 exp002
192.168.20.102 exp003
```

**注意：hosts文件中主管理节点必须放在头部。**

2.  共享文件系统，用于安装AIP文件和容错，缺省：/opt/skyformai_shared。

3.  统一的用户认证系统：LDAP、AD、NIS、或各节点相同用户名和ID的本地用户。指定一个集群主管理员，缺省：cadmin。

4.  所有内网（节点间）关闭防火墙

5.  指定一个联外网的节点作为Web服务器，关闭SELINUX

```
setenforce 0
sed -i s/SELINUX=enforcing/SELINUX=disabled/ /etc/selinux/config
```

Web服务器上安装php, python3, python36-numpy, php-pecl-yaml (现需要安装epel-release)

## 安装

安装分三步：

1.  把文件拷贝到共享文件系统中

2.  在每个节点上设置AIP服务和运行环境

3.  安装web界面

### 拷贝文件

1.  解压下载的文件：

```
mkdir aip
tar xfz skyformaip-9.xx.x.tar.gz -C aip
cp hosts aip
```

2.  运行安装脚本

```
# cd aip
./install
```
若不用缺省的路径、cadmin作为主管理员，参考./install --help显示的命令行参数

### 每个节点上的设置

在每个节点上运行host-setup。这个脚本安装在AIP共享目录中，缺省/opt/skyformai_shared。

```
/opt/skyformai_shared/host-setup
```

### 安装web界面

```
./aip-portal.run
```

## 测试

登录成普通用户

1)  检查集群状态：

```
aip cluster info 或简写 aip c i
```

或SLURM命令：

```
sinfo
```

2)  递交作业

SLURM命令方式

```
$ sbatch  
#!/bin/bash  
sleep 1h  
^D
Submitted batch job 4342

$ squeue
JOBID PARTITION NAME USER ST TIME NODES NODELIST(REASON)
4342 medium sleep 100 cadmin R 0:04 1 linux7

$ scancel 4342
```

LSF命令方式

```
$ bsub -I hostname
Job <4343> is submitted to default queue <medium>.
Job 4343 is waiting to be started...
Job 4343 has started on host linux7.
linux7
```

## Web界面

AIP的web登录使用Linux里的用户名和密码。浏览器连接到: http://\<服务器\>
