# Error on launching
## Error:
* [FATAL] [1598170671.089197390]: Could not wake up Gazebo.
  [firefly/hovering_example-7] process has died [pid 11236, exit code 255, cmd /home/piyush/ros_ws3/devel/lib/rotors_gazebo/hovering_example __name:=
  hovering_example __log:=/home/piyush/.ros/log/1b5faae0-e519-11ea-9254-d0abd521f44e/firefly-hovering_example-7.log].
  log file: /home/piyush/.ros/log/1b5faae0-e519-11ea-9254-d0abd521f44e/firefly-hovering_example-7*.log
### Command: `roslaunch dock_detector default.launch` 
## Solution:
* Just include this line in bashrc file `export GAZEBO_MODEL_PATH=${GAZEBO_MODEL_PATH}:~/iarc_ws/src/IARC2020/iarc_simulation_tools/iarc_simulation_tools/models`
  and the error is resolved.
## Explanation:
* Model path for the custom models that were used from iarc_simulation_tools were not specified inside the bashrc. Initially we used to specify it inside the 
  launch file itself but as we moved we encountered some clashes due to the path. We found that after removing the model path from launch file and including it inside
  the bashrc sorts out the problem and hence we did the same. So after specifying the model path ,the above error was resolved.

# Resolving errors while specifying the path of the directory
### Error while launching roslaunch dubins_trajcetory_generator fw_quadplane.launch
piyush@piyush-Nitro-AN515-54:~/iarc_ws/src/IARC2020/iarc_trajectory_estimation/dubins_trajectory_generator/launch$ roslaunch dubins_trajectory_generator fw_testing.launch 
... logging to /home/piyush/.ros/log/b688d6dc-f102-11ea-8d93-d0abd521f44e/roslaunch-piyush-Nitro-AN515-54-31503.log
Checking log directory for disk usage. This may take a while.
Press Ctrl-C to interrupt
Done checking log file disk usage. Usage is <1GB.

Resource not found: px4
ROS path [0]=/opt/ros/melodic/share/ros
ROS path [1]=/home/piyush/ros_ws3/src/catkin_simple
ROS path [2]=/home/piyush/ros_ws3/src/ariitk_auto_landing/auto_landing
ROS path [3]=/home/piyush/ros_ws3/src/ariitk_auto_landing/detection
ROS path [4]=/home/piyush/ros_ws3/src/eigen_catkin
ROS path [5]=/home/piyush/ros_ws3/src/glog_catkin
ROS path [6]=/home/piyush/ros_ws3/src/eigen_checks
ROS path [7]=/home/piyush/ros_ws3/src/mav_comm/mav_comm
ROS path [8]=/home/piyush/ros_ws3/src/mav_comm/mav_msgs
ROS path [9]=/home/piyush/ros_ws3/src/mav_control_rw/mav_control_interface
ROS path [10]=/home/piyush/ros_ws3/src/mav_control_rw/mav_disturbance_observer
ROS path [11]=/home/piyush/ros_ws3/src/mav_control_rw/mav_linear_mpc
ROS path [12]=/home/piyush/ros_ws3/src/mav_control_rw/mav_lowlevel_attitude_controller
ROS path [13]=/home/piyush/ros_ws3/src/mav_control_rw/mav_nonlinear_mpc
ROS path [14]=/home/piyush/ros_ws3/src/mav_comm/mav_planning_msgs
ROS path [15]=/home/piyush/ros_ws3/src/mav_comm/mav_state_machine_msgs
ROS path [16]=/home/piyush/ros_ws3/src/mav_comm/mav_system_msgs
ROS path [17]=/home/piyush/ros_ws3/src/mav_trajectory_generation/mav_visualization
ROS path [18]=/home/piyush/ros_ws3/src/nlopt
ROS path [19]=/home/piyush/ros_ws3/src/ariitk_auto_landing/pose_estimation
ROS path [20]=/home/piyush/ros_ws3/src/ariitk_auto_landing/pose_estimation_ros
ROS path [21]=/home/piyush/ros_ws3/src/rosfmt
ROS path [22]=/home/piyush/ros_ws3/src/rosmon/rosmon_msgs
ROS path [23]=/home/piyush/ros_ws3/src/rosmon/rosmon_core
ROS path [24]=/home/piyush/ros_ws3/src/rosmon/rqt_rosmon
ROS path [25]=/home/piyush/ros_ws3/src/rosmon/rosmon
ROS path [26]=/home/piyush/ros_ws3/src/unique_identifier/unique_identifier
ROS path [27]=/home/piyush/ros_ws3/src/unique_identifier/uuid_msgs
ROS path [28]=/home/piyush/ros_ws3/src/unique_identifier/unique_id
ROS path [29]=/home/piyush/ros_ws3/src/yaml_cpp_catkin
ROS path [30]=/home/piyush/ros_ws3/src/mav_trajectory_generation/mav_trajectory_generation
ROS path [31]=/home/piyush/ros_ws3/src/mav_trajectory_generation/mav_trajectory_generation_ros
ROS path [32]=/home/piyush/ros_ws3/src/mav_trajectory_generation/mav_trajectory_generation_example
ROS path [33]=/home/piyush/ros_ws3/src/ariitk_auto_landing/tracking
ROS path [34]=/home/piyush/iarc_ws/src/IARC2020/iarc_detection_modules/detector_msgs
ROS path [35]=/home/piyush/iarc_ws/src/IARC2020/iarc_trajectory_estimation/dubins_trajectory_generator
ROS path [36]=/home/piyush/iarc_ws/src/IARC2020/iarc_detection_modules/feature_detection
ROS path [37]=/home/piyush/iarc_ws/src/IARC2020/iarc_detection_modules/iarc_detection_modules
ROS path [38]=/home/piyush/iarc_ws/src/IARC2020/iarc_simulation_tools/iarc_gripper_plugin
ROS path [39]=/home/piyush/iarc_ws/src/IARC2020/iarc_simulation_tools/iarc_magnet_plugin
ROS path [40]=/home/piyush/iarc_ws/src/IARC2020/iarc_mission_nine
ROS path [41]=/home/piyush/iarc_ws/src/IARC2020/iarc_simulation_tools/iarc_simulation_msgs
ROS path [42]=/home/piyush/iarc_ws/src/IARC2020/iarc_simulation_tools/iarc_sim_test_tools
ROS path [43]=/home/piyush/iarc_ws/src/IARC2020/iarc_simulation_tools/iarc_state_plugins
ROS path [44]=/home/piyush/iarc_ws/src/IARC2020/iarc_simulation_tools/iarc_wave_sim/iarc_wave_sim
ROS path [45]=/home/piyush/iarc_ws/src/IARC2020/iarc_simulation_tools/iarc_wave_sim/iarc_wave_sim_gazebo
ROS path [46]=/home/piyush/iarc_ws/src/IARC2020/iarc_simulation_tools/iarc_wave_sim/iarc_wave_sim_gazebo_plugins
ROS path [47]=/home/piyush/iarc_ws/src/IARC2020/iarc_simulation_tools/iarc_simulation_tools
ROS path [48]=/home/piyush/iarc_ws/src/IARC2020/iarc_detection_modules/kfast_iarc
ROS path [49]=/home/piyush/iarc_ws/src/IARC2020/iarc_detection_modules/led_detector
ROS path [50]=/home/piyush/iarc_ws/src/IARC2020/iarc_detection_modules/plate_detector
ROS path [51]=/home/piyush/iarc_ws/src/IARC2020/iarc_detection_modules/pose_estimator
ROS path [52]=/home/piyush/catkin_ws/src/catkin_boost_python_buildtool/catkin_boost_python_buildtool
ROS path [53]=/home/piyush/catkin_ws/src/catkin_simple
ROS path [54]=/home/piyush/catkin_ws/src/catkin_boost_python_buildtool/catkin_boost_python_buildtool_test
ROS path [55]=/home/piyush/catkin_ws/src/eigen_catkin
ROS path [56]=/home/piyush/catkin_ws/src/gflags_catkin
ROS path [57]=/home/piyush/catkin_ws/src/glog_catkin
ROS path [58]=/home/piyush/catkin_ws/src/ceres_catkin
ROS path [59]=/home/piyush/catkin_ws/src/eigen_checks
ROS path [60]=/home/piyush/catkin_ws/src/mav_comm/mav_comm
ROS path [61]=/home/piyush/catkin_ws/src/mav_comm/mav_msgs
ROS path [62]=/home/piyush/catkin_ws/src/mav_nonlinear_mpc/mav_control_interface
ROS path [63]=/home/piyush/catkin_ws/src/mav_nonlinear_mpc/mav_disturbance_observer
ROS path [64]=/home/piyush/catkin_ws/src/mav_nonlinear_mpc/mav_lowlevel_attitude_controller
ROS path [65]=/home/piyush/catkin_ws/src/mav_nonlinear_mpc/mav_nonlinear_mpc
ROS path [66]=/home/piyush/catkin_ws/src/mav_comm/mav_planning_msgs
ROS path [67]=/home/piyush/catkin_ws/src/mav_comm/mav_state_machine_msgs
ROS path [68]=/home/piyush/catkin_ws/src/mav_comm/mav_system_msgs
ROS path [69]=/home/piyush/catkin_ws/src/mav_trajectory_generation/mav_visualization
ROS path [70]=/home/piyush/catkin_ws/src/mav_voxblox_planning/mav_voxblox_planning
ROS path [71]=/home/piyush/catkin_ws/src/minkindr/minkindr
ROS path [72]=/home/piyush/catkin_ws/src/minkindr_ros/minkindr_conversions
ROS path [73]=/home/piyush/catkin_ws/src/nlopt
ROS path [74]=/home/piyush/catkin_ws/src/numpy_eigen
ROS path [75]=/home/piyush/catkin_ws/src/minkindr/minkindr_python
ROS path [76]=/home/piyush/catkin_ws/src/protobuf_catkin
ROS path [77]=/home/piyush/catkin_ws/src/voxblox/voxblox
ROS path [78]=/home/piyush/catkin_ws/src/voxblox/voxblox_msgs
ROS path [79]=/home/piyush/catkin_ws/src/voxblox/voxblox_rviz_plugin
ROS path [80]=/home/piyush/catkin_ws/src/voxblox/voxblox_ros
ROS path [81]=/home/piyush/catkin_ws/src/mav_voxblox_planning/voxblox_skeleton
ROS path [82]=/home/piyush/catkin_ws/src/yaml_cpp_catkin
ROS path [83]=/home/piyush/catkin_ws/src/mav_trajectory_generation/mav_trajectory_generation
ROS path [84]=/home/piyush/catkin_ws/src/mav_voxblox_planning/loco_planner
ROS path [85]=/home/piyush/catkin_ws/src/mav_voxblox_planning/mav_planning_common
ROS path [86]=/home/piyush/catkin_ws/src/mav_voxblox_planning/mav_planning_rviz
ROS path [87]=/home/piyush/catkin_ws/src/mav_trajectory_generation/mav_trajectory_generation_ros
ROS path [88]=/home/piyush/catkin_ws/src/mav_voxblox_planning/mav_path_smoothing
ROS path [89]=/home/piyush/catkin_ws/src/mav_trajectory_generation/mav_trajectory_generation_example
ROS path [90]=/home/piyush/catkin_ws/src/mav_voxblox_planning/voxblox_planning_common
ROS path [91]=/home/piyush/catkin_ws/src/mav_voxblox_planning/voxblox_loco_planner
ROS path [92]=/home/piyush/catkin_ws/src/mav_voxblox_planning/mav_local_planner
ROS path [93]=/home/piyush/ros_ws2/src/catkin_simple
ROS path [94]=/home/piyush/ros_ws2/src/ariitk_planning_library/frontier_explorer
ROS path [95]=/home/piyush/ros_ws2/src/rotors_simulator/rotors_comm
ROS path [96]=/home/piyush/ros_ws2/src/rotors_simulator/rotors_control
ROS path [97]=/home/piyush/ros_ws2/src/rotors_simulator/rotors_description
ROS path [98]=/home/piyush/ros_ws2/src/rotors_simulator/rotors_evaluation
ROS path [99]=/home/piyush/ros_ws2/src/rotors_simulator/rotors_gazebo_plugins
ROS path [100]=/home/piyush/ros_ws2/src/rotors_simulator/rotors_gazebo
ROS path [101]=/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface
ROS path [102]=/home/piyush/ros_ws2/src/rotors_simulator/rotors_joy_interface
ROS path [103]=/home/piyush/ros_ws2/src/rotors_simulator/rotors_simulator
ROS path [104]=/home/piyush/ros_ws2/src/rotors_simulator/rqt_rotors
ROS path [105]=/home/piyush/ros_ws2/src/ariitk_planning_library/simulator
ROS path [106]=/home/piyush/ros_ws2/src/ariitk_planning_library/voxblox_global_planner
ROS path [107]=/opt/ros/melodic/share
The traceback for the exception was written to the log file

So what I did next is that I kept the same launch file that I was including (mavros_posix_sitl.launch) inside my dubins_trajectory_generator and then did 
the launch again.But again encounntered an error which has been pasted below:

piyush@piyush-Nitro-AN515-54:~/iarc_ws/src/IARC2020/iarc_trajectory_estimation/dubins_trajectory_generator/launch$ roslaunch dubins_trajectory_generator fw_testing.launch 
... logging to /home/piyush/.ros/log/6617d49a-f103-11ea-8d93-d0abd521f44e/roslaunch-piyush-Nitro-AN515-54-31734.log
Checking log directory for disk usage. This may take a while.
Press Ctrl-C to interrupt
Done checking log file disk usage. Usage is <1GB.

Resource not found: The following package was not found in <arg default="$(find mavlink_sitl_gazebo)/worlds/empty.world" name="world"/>: mavlink_sitl_gazebo
ROS path [0]=/opt/ros/melodic/share/ros
ROS path [1]=/home/piyush/ros_ws3/src/catkin_simple
ROS path [2]=/home/piyush/ros_ws3/src/ariitk_auto_landing/auto_landing
ROS path [3]=/home/piyush/ros_ws3/src/ariitk_auto_landing/detection
ROS path [4]=/home/piyush/ros_ws3/src/eigen_catkin
ROS path [5]=/home/piyush/ros_ws3/src/glog_catkin
ROS path [6]=/home/piyush/ros_ws3/src/eigen_checks
ROS path [7]=/home/piyush/ros_ws3/src/mav_comm/mav_comm
ROS path [8]=/home/piyush/ros_ws3/src/mav_comm/mav_msgs
ROS path [9]=/home/piyush/ros_ws3/src/mav_control_rw/mav_control_interface
ROS path [10]=/home/piyush/ros_ws3/src/mav_control_rw/mav_disturbance_observer
ROS path [11]=/home/piyush/ros_ws3/src/mav_control_rw/mav_linear_mpc
ROS path [12]=/home/piyush/ros_ws3/src/mav_control_rw/mav_lowlevel_attitude_controller
ROS path [13]=/home/piyush/ros_ws3/src/mav_control_rw/mav_nonlinear_mpc
ROS path [14]=/home/piyush/ros_ws3/src/mav_comm/mav_planning_msgs
ROS path [15]=/home/piyush/ros_ws3/src/mav_comm/mav_state_machine_msgs
ROS path [16]=/home/piyush/ros_ws3/src/mav_comm/mav_system_msgs
ROS path [17]=/home/piyush/ros_ws3/src/mav_trajectory_generation/mav_visualization
ROS path [18]=/home/piyush/ros_ws3/src/nlopt
ROS path [19]=/home/piyush/ros_ws3/src/ariitk_auto_landing/pose_estimation
ROS path [20]=/home/piyush/ros_ws3/src/ariitk_auto_landing/pose_estimation_ros
ROS path [21]=/home/piyush/ros_ws3/src/rosfmt
ROS path [22]=/home/piyush/ros_ws3/src/rosmon/rosmon_msgs
ROS path [23]=/home/piyush/ros_ws3/src/rosmon/rosmon_core
ROS path [24]=/home/piyush/ros_ws3/src/rosmon/rqt_rosmon
ROS path [25]=/home/piyush/ros_ws3/src/rosmon/rosmon
ROS path [26]=/home/piyush/ros_ws3/src/unique_identifier/unique_identifier
ROS path [27]=/home/piyush/ros_ws3/src/unique_identifier/uuid_msgs
ROS path [28]=/home/piyush/ros_ws3/src/unique_identifier/unique_id
ROS path [29]=/home/piyush/ros_ws3/src/yaml_cpp_catkin
ROS path [30]=/home/piyush/ros_ws3/src/mav_trajectory_generation/mav_trajectory_generation
ROS path [31]=/home/piyush/ros_ws3/src/mav_trajectory_generation/mav_trajectory_generation_ros
ROS path [32]=/home/piyush/ros_ws3/src/mav_trajectory_generation/mav_trajectory_generation_example
ROS path [33]=/home/piyush/ros_ws3/src/ariitk_auto_landing/tracking
ROS path [34]=/home/piyush/iarc_ws/src/IARC2020/iarc_detection_modules/detector_msgs
ROS path [35]=/home/piyush/iarc_ws/src/IARC2020/iarc_trajectory_estimation/dubins_trajectory_generator
ROS path [36]=/home/piyush/iarc_ws/src/IARC2020/iarc_detection_modules/feature_detection
ROS path [37]=/home/piyush/iarc_ws/src/IARC2020/iarc_detection_modules/iarc_detection_modules
ROS path [38]=/home/piyush/iarc_ws/src/IARC2020/iarc_simulation_tools/iarc_gripper_plugin
ROS path [39]=/home/piyush/iarc_ws/src/IARC2020/iarc_simulation_tools/iarc_magnet_plugin
ROS path [40]=/home/piyush/iarc_ws/src/IARC2020/iarc_mission_nine
ROS path [41]=/home/piyush/iarc_ws/src/IARC2020/iarc_simulation_tools/iarc_simulation_msgs
ROS path [42]=/home/piyush/iarc_ws/src/IARC2020/iarc_simulation_tools/iarc_sim_test_tools
ROS path [43]=/home/piyush/iarc_ws/src/IARC2020/iarc_simulation_tools/iarc_state_plugins
ROS path [44]=/home/piyush/iarc_ws/src/IARC2020/iarc_simulation_tools/iarc_wave_sim/iarc_wave_sim
ROS path [45]=/home/piyush/iarc_ws/src/IARC2020/iarc_simulation_tools/iarc_wave_sim/iarc_wave_sim_gazebo
ROS path [46]=/home/piyush/iarc_ws/src/IARC2020/iarc_simulation_tools/iarc_wave_sim/iarc_wave_sim_gazebo_plugins
ROS path [47]=/home/piyush/iarc_ws/src/IARC2020/iarc_simulation_tools/iarc_simulation_tools
ROS path [48]=/home/piyush/iarc_ws/src/IARC2020/iarc_detection_modules/kfast_iarc
ROS path [49]=/home/piyush/iarc_ws/src/IARC2020/iarc_detection_modules/led_detector
ROS path [50]=/home/piyush/iarc_ws/src/IARC2020/iarc_detection_modules/plate_detector
ROS path [51]=/home/piyush/iarc_ws/src/IARC2020/iarc_detection_modules/pose_estimator
ROS path [52]=/home/piyush/catkin_ws/src/catkin_boost_python_buildtool/catkin_boost_python_buildtool
ROS path [53]=/home/piyush/catkin_ws/src/catkin_simple
ROS path [54]=/home/piyush/catkin_ws/src/catkin_boost_python_buildtool/catkin_boost_python_buildtool_test
ROS path [55]=/home/piyush/catkin_ws/src/eigen_catkin
ROS path [56]=/home/piyush/catkin_ws/src/gflags_catkin
ROS path [57]=/home/piyush/catkin_ws/src/glog_catkin
ROS path [58]=/home/piyush/catkin_ws/src/ceres_catkin
ROS path [59]=/home/piyush/catkin_ws/src/eigen_checks
ROS path [60]=/home/piyush/catkin_ws/src/mav_comm/mav_comm
ROS path [61]=/home/piyush/catkin_ws/src/mav_comm/mav_msgs
ROS path [62]=/home/piyush/catkin_ws/src/mav_nonlinear_mpc/mav_control_interface
ROS path [63]=/home/piyush/catkin_ws/src/mav_nonlinear_mpc/mav_disturbance_observer
ROS path [64]=/home/piyush/catkin_ws/src/mav_nonlinear_mpc/mav_lowlevel_attitude_controller
ROS path [65]=/home/piyush/catkin_ws/src/mav_nonlinear_mpc/mav_nonlinear_mpc
ROS path [66]=/home/piyush/catkin_ws/src/mav_comm/mav_planning_msgs
ROS path [67]=/home/piyush/catkin_ws/src/mav_comm/mav_state_machine_msgs
ROS path [68]=/home/piyush/catkin_ws/src/mav_comm/mav_system_msgs
ROS path [69]=/home/piyush/catkin_ws/src/mav_trajectory_generation/mav_visualization
ROS path [70]=/home/piyush/catkin_ws/src/mav_voxblox_planning/mav_voxblox_planning
ROS path [71]=/home/piyush/catkin_ws/src/minkindr/minkindr
ROS path [72]=/home/piyush/catkin_ws/src/minkindr_ros/minkindr_conversions
ROS path [73]=/home/piyush/catkin_ws/src/nlopt
ROS path [74]=/home/piyush/catkin_ws/src/numpy_eigen
ROS path [75]=/home/piyush/catkin_ws/src/minkindr/minkindr_python
ROS path [76]=/home/piyush/catkin_ws/src/protobuf_catkin
ROS path [77]=/home/piyush/catkin_ws/src/voxblox/voxblox
ROS path [78]=/home/piyush/catkin_ws/src/voxblox/voxblox_msgs
ROS path [79]=/home/piyush/catkin_ws/src/voxblox/voxblox_rviz_plugin
ROS path [80]=/home/piyush/catkin_ws/src/voxblox/voxblox_ros
ROS path [81]=/home/piyush/catkin_ws/src/mav_voxblox_planning/voxblox_skeleton
ROS path [82]=/home/piyush/catkin_ws/src/yaml_cpp_catkin
ROS path [83]=/home/piyush/catkin_ws/src/mav_trajectory_generation/mav_trajectory_generation
ROS path [84]=/home/piyush/catkin_ws/src/mav_voxblox_planning/loco_planner
ROS path [85]=/home/piyush/catkin_ws/src/mav_voxblox_planning/mav_planning_common
ROS path [86]=/home/piyush/catkin_ws/src/mav_voxblox_planning/mav_planning_rviz
ROS path [87]=/home/piyush/catkin_ws/src/mav_trajectory_generation/mav_trajectory_generation_ros
ROS path [88]=/home/piyush/catkin_ws/src/mav_voxblox_planning/mav_path_smoothing
ROS path [89]=/home/piyush/catkin_ws/src/mav_trajectory_generation/mav_trajectory_generation_example
ROS path [90]=/home/piyush/catkin_ws/src/mav_voxblox_planning/voxblox_planning_common
ROS path [91]=/home/piyush/catkin_ws/src/mav_voxblox_planning/voxblox_loco_planner
ROS path [92]=/home/piyush/catkin_ws/src/mav_voxblox_planning/mav_local_planner
ROS path [93]=/home/piyush/ros_ws2/src/catkin_simple
ROS path [94]=/home/piyush/ros_ws2/src/ariitk_planning_library/frontier_explorer
ROS path [95]=/home/piyush/ros_ws2/src/rotors_simulator/rotors_comm
ROS path [96]=/home/piyush/ros_ws2/src/rotors_simulator/rotors_control
ROS path [97]=/home/piyush/ros_ws2/src/rotors_simulator/rotors_description
ROS path [98]=/home/piyush/ros_ws2/src/rotors_simulator/rotors_evaluation
ROS path [99]=/home/piyush/ros_ws2/src/rotors_simulator/rotors_gazebo_plugins
ROS path [100]=/home/piyush/ros_ws2/src/rotors_simulator/rotors_gazebo
ROS path [101]=/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface
ROS path [102]=/home/piyush/ros_ws2/src/rotors_simulator/rotors_joy_interface
ROS path [103]=/home/piyush/ros_ws2/src/rotors_simulator/rotors_simulator
ROS path [104]=/home/piyush/ros_ws2/src/rotors_simulator/rqt_rotors
ROS path [105]=/home/piyush/ros_ws2/src/ariitk_planning_library/simulator
ROS path [106]=/home/piyush/ros_ws2/src/ariitk_planning_library/voxblox_global_planner
ROS path [107]=/opt/ros/melodic/share


So now the world file was not found this time..So there was no clue what was happening here..What do you think?
## Solution
Actually due to clashes of rotors with px4, I had kept them in seperate directories and while using one I used to clean the workspace containing the other one
and also comment the same workspace in bashrc. So while I was using px4 after using rotors for quite some time, then I did build the Firmware using `make px4_
sitl gazebo` and I did get my px4 launch files working. But again the above launch file was not working. So the reason was that I had not built the workspace 
along with Firmware so due to this my package was not able to get the path of the workspace in which mavros_posix_sitl.launch was situated.
So I built that workspace and then re-launched it..Now that daunting error was not there but again got an error which was a simple one related to the launch 
file which was as below:
`piyush@piyush-Nitro-AN515-54:~$ roslaunch dubins_trajectory_generator fw_testing.launch 
... logging to /home/piyush/.ros/log/87a70578-f10c-11ea-8d93-d0abd521f44e/roslaunch-piyush-Nitro-AN515-54-16642.log
Checking log directory for disk usage. This may take a while.
Press Ctrl-C to interrupt
Done checking log file disk usage. Usage is <1GB.

RLException: unused args [world_name] for include of [/home/piyush/ros_ws/src/Firmware/launch/mavros_posix_sitl.launch]
The traceback for the exception was written to the log file`

So this was resolved once I removed the arg related to the world_name as it was shown in the error (and one of those lines was `<arg name="world_name" default="default"/>` )

And now it was working fine:)

# Resolving error while launching box_detector

piyush@piyush-Nitro-AN515-54:~/drdo_ws/src/inter_iit_dgre_voad$ roslaunch box_detector default.launch
RLException: [default.launch] is neither a launch file in package [box_detector] nor is [box_detector] a launch file name
The traceback for the exception was written to the log file

### Solution:

This launch file was created for the first time so the workspace needed to be sourced. I was launching it without sourcing it and hence was getting that error. Once I opened a new terminal(which is equivalent to sourcing if you have already added the source command in bashrc file). Very simple bug but it's good keep track of every single bug :)
