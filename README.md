# core_perception
Autoware packages related to understanding the state of the world (perception, localisation, object recognition, etc.).

www.autoware.org

* 若是已經 Build 完 Autoware 想改部分的程式碼只需要指定 Package 即可
* 記得要把 `~/autoware.ai/src/autoware/core_perception` 刪除並換成此專案的內容
```
colcon build --packages-select [package name]

# example
colcon build --packages-select lidar_localizer
colcon build --packages-select ndt_cpu
```