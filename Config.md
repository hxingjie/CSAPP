# Config

## config for csapp
```
sudo apt update

sudo apt install git
sudo apt install vim
sudo apt install g++
sudo apt install make
sudo apt install cmake

sudo passwd root
su root

sudo apt install openssh-server // 安装ssh
sudo service ssh start // 启动ssh
sudo ufw disable // 关闭防火墙
sudo service ssh status // 查看状态
sudo apt install net-tools
ifcong // 查看ip

windows -> cmd: ping ip // 检查是否能ping通

windows -> vscode -> install remote-ssh
remote-ssh: config
Host ubuntu-csapp
  HostName 192.168.236.135
  User hxj
  ForwardAgent yes
连接即可
```

## test
vim hello.cpp
```c++
#include <iostream>

int main() {
  std::cout << "hello, world." << std::endl;
  return 0;
}
```
g++ -o hello hello.cpp
./hello
