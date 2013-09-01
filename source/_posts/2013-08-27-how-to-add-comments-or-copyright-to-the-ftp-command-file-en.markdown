---
layout: post
title: "How to Add Comments or Copyright to the Ftp Command File"
date: 2013-08-27 21:58
comments: true
categories: [windows, dos]
tags: [windows, dos, ftp, comment]
---
## Because of
I write a ftp commond file to transfer the file to the ftp server automatically. It is works. Before i commit it the svn repo, i want to add the copyright comments in the header of the file. I add the following comments:
```
@rem/**********************************
@rem copyright @ xxx technology.
@rem author: caiqinghua@gmail.com
@rem modify list:
@rem 2013-08-27 create the file
@rem **********************************/
```

And it doesn't work.

## find the reason
I post a ask to a ask-answer community. Till today, i get a lots of answer and i know the reason.

## how to transfer the file to ftp server automatically and add comments
### how to transfer the file to ftp server automatically

I don't install the english windows in my computer, so you will see some chinese in the echo of the command "ftp /?".

ftp command in the windows dos command. 
```
d:\ruby\octopress>ftp /?

将文件传送到运行 FTP 服务器服务(经常称为后台程序)的计算机以及将文件从该计算机
传出。可以交互使用 Ftp。

FTP [-v] [-d] [-i] [-n] [-g] [-s:filename] [-a] [-A] [-x:sendbuffer] [-r:recvbuf
fer] [-b:asyncbuffers] [-w:windowsize] [host]

  -v              禁止显示远程服务器响应。
  -n              禁止在初始连接时自动登录。
  -i              关闭多文件传输过程中的
                  交互式提示。
  -d              启用调试。
  -g              禁用文件名通配(请参阅 GLOB 命令)。
  -s:filename     指定包含 FTP 命令的文本文件；命令
                  在 FTP 启动后自动运行。
  -a              在绑字数据连接时使用所有本地接口。
  -A              匿名登录。
  -x:send sockbuf 覆盖默认的 SO_SNDBUF 大小 8192。
  -r:recv sockbuf 覆盖默认的 SO_RCVBUF 大小 8192。
  -b:async count  覆盖默认的异步计数 3
  -w:windowsize   覆盖默认的传输缓冲区大小 65535。
  host            指定主机名称或要连接到的远程主机
                  的 IP 地址。

注意:
  - mget 和 mput 命令将 y/n/q 视为 yes/no/quit。
  - 使用 Ctrl-C 中止命令。

d:\ruby\octopress>
```

As you can see, you can use the ftp -s:filename to transfer file to ftp server.

I create a file that named ftpcmd.txt
And write the following content to the file.
```
open 1.1.1.1
admin
admin
ftp a.markdown a.markdown
by
```

If you execute the commond "ftp -s:ftpcmd.txt" in the dos cmd env, it will transfer the a.markdown to the ftp server 1.1.1.1.

### how add the comments in the header of the ftpcommand file

```
!@rem /**********************************
!@rem copyright @ xxx technology.
!@rem author: caiqinghua@gmail.com
!@rem modify list:
!@rem 2013-08-27 create the file
!@rem **********************************/

open 1.1.1.1
admin
admin
ftp a.markdown a.markdown
by
```
You should add the "!" to the begin of the comment line.
And you should add a space character between !@rem and the comment content.

## Conclusions
Linux Unix Os: use the !# to the begin of the comment.
Windows:       use the !@rem to  the begin of the comment.
what is "!"
```
ftp> ! help
ftp> help !
!               转义到 shell
ftp>

```
!go to shell execute this command, so we can use the shell or dos comments syntax.
@ tell the shell don't echo in this command.

More information about ftp transfer file to the server or add comments, please google.

## Chinese version of this post.
I will post the chinese version later.
