## 解决gnutls_handshake() failed问题
- **sudo apt-get update
- **sudo apt-get install build-essential fakeroot dpkg-dev libcurl4-openssl-dev
- **sudo apt-get build-dep git
- **mkdir ~/git-openssl
- **cd ~/git-openssl
- **sudo apt-get source git
- **sudo dpkg-source -x git_2.20.1-2.dsc
- **cd git-2.20.1
## 注意上面的2.20.1要按照你自己的版本文件名进行修改
- **vi debian/control
#找到libcurl4-gnutls-dev，全部替换为libcurl4-openssl-dev
- **sudo dpkg-buildpackage -rfakeroot -b
#如果fail on test，可以将文件debian/rules中的TEST=test注释掉
#最后
- **sudo dpkg -i ../git_2.20.1-2_amd64.deb安装git即可。
## 如果是amd64也可以使用现成我重编译好的deb

 
