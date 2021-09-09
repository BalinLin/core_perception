# core_perception
Autoware packages related to understanding the state of the world (perception, localisation, object recognition, etc.).

www.autoware.org

* [Build From Source](https://www.notion.so/NDT-Installation-b1493865fd7f4adbbe8764e8a1f327fc#16d8e5effd7648e18f2112ec6142fec6)
```
mkdir -p ~/autoware.ai/src
cd ~/autoware.ai
vcs import src < autoware.ai.repos

# Step 4 (如果使用 anaconda/python3 或偵測不到 os 的狀況下)
# rosdep install -y --from-paths src --ignore-src --rosdistro $ROS_DISTRO
rosdep install -y --from-paths src --ignore-src --rosdistro $ROS_DISTRO --os=ubuntu:bionic

# Step 5 (請使用系統的 python2)
# colcon build --cmake-args -DCMAKE_BUILD_TYPE=Release
colcon build --cmake-args -DCMAKE_BUILD_TYPE=Release -DSETUPTOOLS_DEB_LAYOUT=OFF


# ~/.bashrc setting
echo "source ~/autoware.ai/install/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

* 若是已經 build 完 autoware 想改部分的程式碼只需要指定 package 即可
```
colcon build --packages-select [package name]

# example
colcon build --packages-select lidar_localizer
colcon build --packages-select ndt_cpu
```