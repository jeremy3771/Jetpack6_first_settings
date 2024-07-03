# Jetpack6_first_settings
> jetpack setting(pip, torch, ROS2, etc..)

## 1. keyboard(Korean)
- settings -> Region & Language -> Manage... -> sel Korean -> Reboot
- settings -> Keyboard -> add Korean(Hangul)

## 2. install with apt
```shell
sudo apt install terminator
sudo apt install firefox
sudo apt install tree
```

## 3. install ROS2(Humble)
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

source /opt/ros/humble/setup.bash
```

## 4. OpenCV 4.10.0 with CUDA
```shell
./build_opencv.sh
```
