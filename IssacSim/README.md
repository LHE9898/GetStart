# Environment Setup
## 0. Hardware Specification
 - Intel(R) Core(TM) i7-9700KF CPU @ 3.60GHz
 - NVIDIA GeForce RTX 2080 Ti
 - RAM 32GB
 - SSD 500GB

## 1. Setting on Ubuntu
### Install Nvidia Driver
https://www.nvidia.com/download/index.aspx

- 기존 Nvidia Driver와 충돌을 막기위해 Nouveau 비활성화
```
$ sudo apt-get update
$ sudo apt-get remove nvidia* && sudo apt autoremove 
$ sudo apt-get install dkms build-essential linux-headers-generic
$ sudo gedit /etc/modprobe.d/blacklist.conf
```
```
blacklist nouveau
blacklist lbm-nouveau
options nouveau modeset=0
alias nouveau off
alias lbm-nouveau off
```
- nvidia driver install
```
$ sudo update-initramfs -u
$ sudo apt install nvidia-driver-550
$ sudo reboot
$ nvidia-smi
```

### Install Cuda
- run 파일을 다운받아 실행
```
$ wget https://developer.download.nvidia.com/compute/cuda/11.8.0/local_installers/cuda_11.8.0_520.61.05_linux.run
$ sudo sh cuda_11.8.0_520.61.05_linux.run
```

### Install Python
- IssacSim required Python3.10
```install python3.10
$ cd Downloads/Python-3.10.14/
$ ./configure --enable-optimizations
$ sudo make -j4 && sudo make altinstall
$ python3.11 --version
$ python3.11 -m pip --version
```

### Install ROS

## 2. Install Issacsim  
