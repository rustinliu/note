## 本地文件上传到服务器以及服务器文件下载到本地

**一、命令格式：**

 

```
scp [-1246BCpqrv] [-c cipher] [-F ssh_config] [-i identity_file] [-l limit] [-o ssh_option] [-P port] [-S program] [[user@]host1:]file1 [...] [[user@]host2:]file2
```

 

**简易写法：**

```
scp [可选参数] file_source file_target
```

 

　　

**二、参数说明：**

**-1：**强制scp命令使用ssh1

**-2：**强制scp命令使用ssh2

**-4：**强制scp命令只使用IPv4寻址

**-6：**强制scp命令只使用IPv6寻址

**-B：**使用批处理模式（传输过程中不询问传输口令或短语）

**-C：**允许压缩。（将-C标志传递给ssh，从而打开压缩功能）

**-p：**保留源文件的修改时间，访问时间和访问权限

**-q：**不显示传输进度条

**-r：**递归复制整个目录

**-v：**详细方式显示输出。scp和ssh1会显示出整个过程的调试信息。这些信息用于调试连接、验证和配置问题。

**-c：**cipher，以cipher将数据传输进行加密，这个选项将直接传递给ssh

**-F：**ssh_config，指定一个替代的ssh配置文件，此参数直接传递给ssh。

**-i：** identity_file，从指定文件中读取传输时使用的密钥文件，此参数直接传递给ssh。

**-l：**limit，限定用户所能使用的带宽，以Kbit/s为单位。

**-o：**ssh_option，如果习惯于使用ssh_config(5)中的参数传递方式，

**-P：**port，注意是大写的P, port是指定数据传输用到的端口号

**-S：**program，指定加密传输时所使用的程序。此程序必须能够理解ssh(1)的选项。

 

**三、实例：**

**1. 从本地复制到远程服务器**

　　　　**命令格式：**scp –r 本地文件或目录 远程用户名@地址：文件或目录

　　　　**实例：**scp –r /home/1.mp3 root@10.144.144.112:/home/music

　　　　　　(将本地home下的文件1.mp3复制到10.144.144.112服务器下home/music目录下)

　　　　**注：**本地文件可复制到远程目录或文件下，本地目录只能复制到远程目录下。

 

**2. 从远程服务器复制到本地**

**命令格式：**scp –r 远程用户名@地址：文件或目录 本地文件或目录

**实例：**scp –r root@10.144.144.112:/home/music/1.mp3 /home

　　（将远程服务器10.144.144.112下home/music目录下的1.mp3复制到本地home目录下）

**注：**远程文件可复制到本地文件或目录下，远程目录只能复制到本地目录下