# Ubuntu Initial Setup

## nvidia driver install

```bash
# Check graphic card
sudo update-pciids
lspci | grep VGA

# Install appropriate graphic card driver
sudo apt-add-repository ppa:graphics-drivers/ppa 
sudo apt update
ubuntu-drivers devices
sudo ubuntu-drivers autoinstall
```

## .deb program install
chrome, vscode

## apt program install
```bash
sudo apt install terminator -y
sudo apt install simplescreenrecorder -y
```
## terminator key binding setup

ibus-setup에서 emoji 단축키(ctrl+shift+e) 삭제

## (optional) Language Setup
2-1 
2-2 setting-region&language-+ 클릭 후 Korean(Hangul)추가 후 나머지 삭제
2-3 sudo apt install gnome-tweaks -y && gnome-tweaks 실행
2-4 Keyboard&Mouse-AddtionalLayoutOptions-KoreanHangul/Hanjakeys-MakerightAltaHangulkey
2-5 setting-region&language-Korean(Hangul) 톱니 클릭 후 hangul 빼고 다른키 모두 삭제
```bash

```

## Cmake upgrade
[cmake_download_link](https://cmake.org/download/)\
압축해제


```bash
cmake --version

cd ~/Downloads/cmake-3.xxxx/  
./bootstrap --prefix=$HOME/cmake-install
make
make install
echo "export PATH=$HOME/cmake-install/bin:$PATH" >> ~/.bashrc
echo "export CMAKE_PREFIX_PATH=$HOME/cmake-install:$CMAKE_PREFIX_PATH" >> ~/.bashrc

cmake --version

```


## Cmake upgrade

5. 도커 설치
https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository
# 도커 명령어에 sudo 안붙이도록
sudo usermod -aG docker $USER
sudo reboot

6. nvidia-container-toolkit 설치 (https://velog.io/@cjw9105/NVIDIA-Container-Toolkit-%EC%84%A4%EC%B9%98)

https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html


 #install 후에 runtime 추가하는 법
sudo mkdir -p /etc/systemd/system/docker.service.d
sudo tee /etc/systemd/system/docker.service.d/override.conf <<EOF
[Service]
ExecStart=
ExecStart=/usr/bin/dockerd --host=fd:// --add-runtime=nvidia=/usr/bin/nvidia-container-runtime
EOF
sudo systemctl daemon-reload \
  && sudo systemctl restart docker
sudo nvidia-ctk runtime configure --runtime=docker
sudo systemctl restart docker
sudo docker run --rm --runtime=nvidia --gpus all nvidia/cuda:11.8.0-base-ubuntu20.04 nvidia-smi

6. ros 설치
!!!!!!!!!!!!!!
pcl은 ros 설치하면서 자동으로 설치가 된다. pcl 제거 하거나 새로 버전 설치하면 꼬일 수 있음 주의!!!!!!!!!!!!
python3-pcl만 설치해주면 된다.
python3
import pcl
a = pcl.PointCloud()
로 잘 설치 됬는지 확인


