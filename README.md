# Jetpack 6.0 first settings
> jetpack setting(pip, torch, ROS2, etc..)

## 1. default settings
#### suspend
- settings -> Power -> Screen Blank: Never
#### keyboard(Korean)
- settings -> Region & Language -> Manage... -> sel Korean -> Reboot
- settings -> Keyboard -> add Korean(Hangul)

## 2. install with apt and pip
```shell
sudo apt install terminator
sudo apt install firefox
sudo apt install tree
sudo apt install python3-pip
sudo -H pip install -U jetson-stats
pip3 install onnx
pip install ultralytics
```

## 3. install ROS2(Humble)
> https://docs.ros.org/en/humble/index.html
```shell
sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8

sudo apt install software-properties-common
sudo add-apt-repository universe

echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null

sudo apt update
sudo apt upgrade

sudo apt install ros-humble-desktop
sudo apt install ros-humble-ros-base
sudo apt install ros-dev-tools

echo 'source /opt/ros/humble/setup.bash' >> ~/.bashrc
```

## 4. OpenCV 4.10.0 with CUDA
#### check OpenCV with CUDA by jtop
```shell
./build_opencv.sh
```

## 5. torch with CUDA
> https://forums.developer.nvidia.com/t/pytorch-for-jetson/72048
#### check torch with CUDA is available
```shell
>>> import torch
>>> torch.cuda.is_available()
```
#### if return is False
```shell
wget https://nvidia.box.com/shared/static/mp164asf3sceb570wvjsrezk1p4ftj8t.whl -O torch-2.3.0-cp310-cp310-linux_aarch64.whl
wget https://nvidia.box.com/shared/static/9agsjfee0my4sxckdpuk9x9gt8agvjje.whl -O torchaudio-2.3.0+952ea74-cp310-cp310-linux_aarch64.whl
wget https://nvidia.box.com/shared/static/xpr06qe6ql3l6rj22cu3c45tz1wzi36p.whl -O torchvision-0.18.0a0+6043bc2-cp310-cp310-linux_aarch64.whl
sudo apt-get install python3-pip libopenblas-base libopenmpi-dev libomp-dev
pip3 install 'Cython<3'
pip3 install numpy torch-2.3.0-cp310-cp310-linux_aarch64.whl torchaudio-2.3.0+952ea74-cp310-cp310-linux_aarch64.whl torchvision-0.18.0a0+6043bc2-cp310-cp310-linux_aarch64.whl
```

## 6. Livox MID-360
