# GridBased_FastSLAM_ROS
Using gmapping ROS package to perform FastSLAM algorithm 

to run follow next steps
1. Clone repository inside your `~/{catkin_workspace}/src`
`git clone https://github.com/AmarYasser/GridBased_FastSLAM_ROS.git`

2. Install the dependencies and build the workspace
```
cd ~/{catkin_workspace}
source devel/setup.bash
rosdep -i install turtlebot_gazebo
rosdep -i install turtlebot_teleop
rosdep install gmapping
catkin_make
source devel/setup.bash
```
3. Launch the needed nodes in seperate shells

- Gazebo world
 
 `roslaunch turtlebot_gazebo turtlebot_world.launch world_file:=worlds/willowgarage.world`

- Rviz 
  `rviz rviz`

You can use the configured .rviz file included

- Teleop

  `roslaunch turtlebot_teleop keyboard_teleop.launch`

- SLAM

  `rosrun gmapping slam_gmapping`
  
- Map Server
 `rosrun map_server map_saver -f myMap`
 
 With the map_server you can load and save maps. Running map_server will generate the map.pgm and the map.yaml files
