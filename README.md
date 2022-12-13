
# PX4_RTABMAP_ROS2

this is repository for simulating rtabmap with ros2 interface


git clone https://github.com/Amiraqaie/PX4_RTABMAP_ROS2.git

cd PX4_RTABMAP_ROS2

tar -xvf models.tar.xz

export GAZEBO_MODEL_PATH=<Current_Path_to_PX4_Root>:${GAZEBO_MODEL_PATH}

make px4_sitl_rtps gazebo_droneai__apt

CTRL+SHIFT+T

cd droneai_tf_publisher

ros2 launch robot_state_publisher.launch.py

dependecie : 
	1. install rtabmap for ros2 from https://github.com/introlab/rtabmap_ros
	2. build and source the rtabmap repository in you terminal

CTRL+SHIFT+T

ros2 launch rtabmap_ros rtabmap.launch.py  args:="-d --Optimizer/GravitySigma 0.1 --Vis/FeatureType 10 --Kp/DetectorStrategy 10 --Grid/MapFrameProjection true --NormalsSegmentation false --Grid/MaxGroundHeight 1 --Grid/MaxObstacleHeight 1.6 --RGBD/StartAtOrigin true"  use_sim_time:=true rgb_topic:=/camera/image_raw depth_topic:=/camera/depth/image_raw camera_info_topic:=/camera/camera_info imu_topic:=/imu approx_sync:=true  qos:=1  rtabmapviz:=false

now open the QGroundControl or use MAVproxy command to drive your drone	

