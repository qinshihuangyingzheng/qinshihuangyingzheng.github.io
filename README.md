看摄像头的相关信息

[百度](http://www.baidu.com)

[我的博客](https://github.com/qinshihuangyingzheng/qinshihuangyingzheng.github.io/edit/master/README)

lshal | grep Cam

 

dmesg  | grep Cam

 

dmesg | grep video

ref: https://wenku.baidu.com/view/1b68c68b71fe910ef12df80f.html

 

获取照片：
==
sudo apt-get install streamer

streamer -f jpeg -o image.jpeg

streamer –h 获取帮助信息

 

python实现，并将图片时间作为文件名保存

import time

import os

picture_time = time.strftime("%Y%m%d_%H%M%S", time.localtime())

os.system("streamer -s 640x480 -o /home/arm/python/picture/" + picture_time +".jpeg") 

 

ref: https://askubuntu.com/questions/106770/take-a-picture-from-terminal

 

friendlyarm 4418 com3 -> /dev/ttyAMA3

linux取消输入密码：passwd -d root

 

 

linux 开机自启动：

开机之后会执行/etc/rc.local文件中的脚本，所以我们可以直接在/etc/rc.local中添加启动脚本。当然要添加到语句：exit 0 前面才行。

sudo vi /etc/rc.local 

# 进去文件内部，按a进行编辑，在exit 0 前面输入

# 开启远程桌面

/etc/init.d/xrdp start

 

# 开启文件共享

sudo systemctl start smbd

sudo systemctl start nmbd

# 按esc退出编辑模式，输入：wq! 保存退出

vi /etc/init.d  # 查看启动项

 

ref: https://www.jb51.net/os/Ubuntu/181138.html

 

普中科技开发板资料：https://pan.baidu.com/s/1qYGdJ4K#list/path=%2F

Roof_greening_5.0_arm.py  8.23 21:30-8.24 10:00在arm测试 OK(最后sleep60s)

在linux上 终端运行时，python xxx.py & 终端关闭时程序仍然继续运行

 

2018年9月14日 星期五

网络中心 dell R730安装 VMware ESXi 6.0.0

10.66.2.212

下载

串口助手使用stc-isp为好，经过测试

 

sudo: unable to resolve host [hostname]

/etc/hosts

在第一行下方加入：fa

127.0.0.1   [hostname]

Ref: https://blog.csdn.net/github_38236333/article/details/78453773

 

http://blog.chinaunix.net/uid-2282111-id-2113216.html

 

串口助手使用stc-isp为好，经过测试

 

EMC(Electro Magnetic Compatibility) 电磁兼容

EMI(Electro Magnetic Interference) 电磁干扰

 

PT100: PT100温度传感器又叫做铂热电阻，0℃时阻值为100欧姆，在100℃时它的阻值约为138.5欧姆。它的阻值会随着温度上升而成近似匀速的增长。

 

      i超前u,阻抗角为正，感性capacitive (negative phase shift)

      u

  


      i滞后u,阻抗角为负，容性inductive (positive phase shift)

 

安装pip

wget https://bootstrap.pypa.io/get-pip.py 

sudo python3 get-pip.py

 

https://blog.csdn.net/howsoever/article/details/79257002

 

 

pip清华pip镜像

pip install pip -U

pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple

 

https://mirrors.tuna.tsinghua.edu.cn/help/pypi/

 

 

安装serial

sudo pip3 install serial

 

安装pymysql出现Failed cleaning build dir for cryptography等

sudo apt-get update

sudo apt-get install python3-dev python-pip libxml2-dev libxslt1-dev zlib1g-dev libffi-dev libssl-dev

sudo pip3 install pymysql

 

https://blog.csdn.net/q_an1314/article/details/51424849

sudo 免密码：

用 visudo 编辑 sudo 的权限，给指定的用户无需密码

sudo visudo

fa ALL=(ALL:ALL) ALL 用#注释掉，新加

fa ALL=(ALL) NOPASSWD: ALL

REF: https://blog.csdn.net/white__cat/article/details/34415709

    https://blog.csdn.net/tty521/article/details/61422791
  远程访问arm终端
  操作命令ssh fa@10.0.0.114 删除文件
  复制本地文件到登陆arm sftp fa@10.0.0.114
