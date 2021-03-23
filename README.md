# moveit_gazebo_demo

## Installation

### Dependencies
```
sudo apt install python3-wstool python3-catkin-tools python3-rosdep
```

### Workspace setup
```
source /opt/ros/noetic/setup.bash
mkdir -p ~/demo_ws
cd ~/demo_ws
wstool init src https://raw.githubusercontent.com/ipa-hsd/moveit_gazebo_demo/main/demo.rosinstall
rosdep update
rosdep install --from-paths src --ignore-src -r -y
catkin build
source ~/demo_ws/devel/setup.bash
```

## Usage
Terminal 1
```
source ~/demo_ws/devel/setup.bash
roslaunch ur_gazebo ur5_joint_limited.launch
```
Terminal 2
```
source ~/demo_ws/devel/setup.bash
roslaunch ur5_moveit_config ur5_moveit_planning_execution.launch sim:=true
```
Terminal 3
```
source ~/demo_ws/devel/setup.bash
rviz
```
To plan and execute trajectories in `RViz`, please follow the instructions in [MoveIt tutorials](https://ros-planning.github.io/moveit_tutorials/doc/quickstart_in_rviz/quickstart_in_rviz_tutorial.html)
