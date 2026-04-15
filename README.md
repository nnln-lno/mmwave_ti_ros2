# Custom package for TI mmwave radar 
REF : <https://github.com/kimsooyoung/mmwave_ti_ros>

## 0. Prerequisite
✅ ROS 2 (Ubuntu 22.04 with Humble Distro)  
  
## 1. How to use and build ?

   - In ros2 workspace directory (ex. ros2_ws/src)
   ```
   $ git clone https://github.com/nnln-lno/mmwave_ti_ros2.git
   ```

   - Change to workspace directory. (ex. ros2_ws)
   ```
   $ # Please follow the order carefully
   $ colcon build --packages-select serial
   $ source install/setup.bash
   $
   $ colcon build --packages-select ti_mmwave_ros2_intefaces
   $ source install/setup.bash
   $
   $ colcon build --packages-select ti_mmwave_ros2_pkg
   $ source install/setup.bash
   ```

## 2. How to run and configure the packages? 

   - About Configuration, put the configuration file in below directory. 
   ```
   $ cd ros2_ws/src/mmwave_ti_ros/ti_mmwave_ros2_pkg/cfg
   ```

   - In launch file, apply the configuration which user want to use.

     Change the "cfg_file" variable to desired config file name in cfg folder.
   ```
   $ cd ros2_ws/src/mmwave_ti_ros/ti_mmwave_ros2_pkg/launch
   $ sudo nano incsl.launch.py
   ```

   - In launch file, apply the configuration which user want to use.
   ```
   $ cfg_file = "<name of config file>"
   ```

   - Almost done! launch the file and check the pointcloud.
   ```
   $ ros2 launch ti_mmwave_ros2_pkg incsl.launch.py
   ```

## 3. Check the point cloud in rviz2
   - Set the fixed frame name to "ti_mmwave"
   - Add Pointcloud2 and select the correct topic name.
