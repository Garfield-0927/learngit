# 公钥私钥无密码登录服务器的实现

## 0. 准备工作

以win10为例，在应用商店中即可下载Windows terminal，具体步骤如下：

[![aMmnoR.md.png](https://s1.ax1x.com/2020/07/30/aMmnoR.md.png)](https://imgchr.com/i/aMmnoR)

[![aMmFzT.md.png](https://s1.ax1x.com/2020/07/30/aMmFzT.md.png)](https://imgchr.com/i/aMmFzT)

Windows terminal操作界面：

[![aMmmw9.md.png](https://s1.ax1x.com/2020/07/30/aMmmw9.md.png)](https://imgchr.com/i/aMmmw9)

## 1. 在本地机器上使用ssh-keygen产生公钥私钥对

（1）命令如下：``ssh-keygen``。输入完命令后一直敲回车即可。

[![aMmiWV.md.png](https://s1.ax1x.com/2020/07/30/aMmiWV.md.png)](https://imgchr.com/i/aMmiWV)

（2）进入上图中生成key的目录，可以发现有``id_rsa``以及``id_rsa.pub``两个文件。

[![aMmEyF.md.png](https://s1.ax1x.com/2020/07/30/aMmEyF.md.png)](https://imgchr.com/i/aMmEyF)

## 2. 将公钥复制到远程机器中

（1）由于我的机子是win10的系统，无法执行``ssh-copy-id``的命令，于是我们手动将我们的公钥复制到服务器上。我们这里用windows
terminal来连接服务器。

执行ssh 用户名\@IP，再输入密码，即可连接上服务器。

注：我们的目标是将公钥拷贝到服务器上的
.ssh/authorized_keys中，服务器原本没有.ssh目录，自己创建会涉及到权限问题，于是我们再服务器上执行ssh-keygen来生成
.ssh目录。

[![aMmAQU.md.png](https://s1.ax1x.com/2020/07/30/aMmAQU.md.png)](https://imgchr.com/i/aMmAQU)

（2）进入到刚创建的.ssh目录下，需要注意的是，这个
.ssh目录并不是生成在根目录下，而是生成在根目录下的root目录下。

[![aMmeeJ.md.png](https://s1.ax1x.com/2020/07/30/aMmeeJ.md.png)](https://imgchr.com/i/aMmeeJ)

（3）进入到
.ssh目录下后，发现并没有authorized_keys，我们用touch命令手动创建即可。再用vim命令进行文件修改，将我们的公钥复制到authorized_keys中，然后esc，再输入：wq保存即可。

[![aMmMJx.md.png](https://s1.ax1x.com/2020/07/30/aMmMJx.md.png)](https://imgchr.com/i/aMmMJx)

[![aMmKF1.md.png](https://s1.ax1x.com/2020/07/30/aMmKF1.md.png)](https://imgchr.com/i/aMmKF1)

公钥实例如上图

[![aMmVL4.md.png](https://s1.ax1x.com/2020/07/30/aMmVL4.md.png)](https://imgchr.com/i/aMmVL4)

（4）执行完上述步骤之后，即可实现无需密码连接云服务器啦！

# 大功告成，验收成果！

我们先退出服务器，再施行ssh 用户名\@IP命令重新连接。

再次连接无需输入密码，解放你的双手！！！

[![aMmPJ0.png](https://s1.ax1x.com/2020/07/30/aMmPJ0.png)](https://imgchr.com/i/aMmPJ0)

[![aMmQW6.md.png](https://s1.ax1x.com/2020/07/30/aMmQW6.md.png)](https://imgchr.com/i/aMmQW6)