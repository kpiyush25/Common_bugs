# 1.Resolving errors while building iarc_simulation_tools
### Error while building the package for the first time
* Errors     << iarc_simulation_tools:check /home/piyush/iarc_ws/logs/iarc_simulation_tools/build.check.000.log
  CMake Error: The source directory "/home/piyush/iarc_ws/src/IARC2020/iarc_simulation_tools" does not appear to contain CMakeLists.txt.
  Specify --help for usage, or press the help button on the CMake GUI.
  make: *** [cmake_check_build_system] Error 1

### Error while building the package for the second time
* Errors     << iarc_gripper_plugin:make /home/piyush/iarc_ws/logs/iarc_gripper_plugin/build.make.002.log                                                                                                    
  /home/piyush/iarc_ws/src/IARC2020/iarc_simulation_tools/iarc_gripper_plugin/src/gripper_plugin.cpp:1:10: fatal error: 
  iarc_gripper_plugin/GripperCmd.h: No such file or directory
  #include <iarc_gripper_plugin/GripperCmd.h>
           ^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
  compilation terminated.
  make[2]: *** [CMakeFiles/iarc_gripper_plugin.dir/src/gripper_plugin.cpp.o] Error 1
  make[1]: *** [CMakeFiles/iarc_gripper_plugin.dir/all] Error 2
  make[1]: *** Waiting for unfinished jobs....
  make: *** [all] Error 2

### Error while building the package for the third time
* Errors     << iarc_gripper_plugin:make /home/piyush/iarc_ws/logs/iarc_gripper_plugin/build.make.000.log                                                                                                    
  In file included from /home/piyush/iarc_ws/src/IARC2020/iarc_simulation_tools/iarc_gripper_plugin/src/gripper_plugin.cpp:1:0:
  /home/piyush/iarc_ws/devel/.private/iarc_gripper_plugin/include/iarc_gripper_plugin/GripperCmd.h:12:10: fatal error: 
  iarc_gripper_plugin/GripperCmdResponse.h: No such file or directory
  #include <iarc_gripper_plugin/GripperCmdResponse.h>
            ^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
  compilation terminated.
  make[2]: *** [CMakeFiles/iarc_gripper_plugin.dir/src/gripper_plugin.cpp.o] Error 1
  make[1]: *** [CMakeFiles/iarc_gripper_plugin.dir/all] Error 2
  make[1]: *** Waiting for unfinished jobs....
  make: *** [all] Error 2

## Solution:
* Actually the package contained some custom message files,which are created only when we build the package. So here in this case we 
  can see that different errors come while building at different times which means that each time we build ,some of the custom message
  files are created and hence once all the custom message files are created ,there is no build error.
* So the only thing that needs to be done in such cases is to build again and again and eventually you get no such errors.


# 2. Resolving errors while building rotors_simulator
### (Branch was feature/fw_hil_rotors, everything was fine on master)

Errors     << rotors_gazebo_plugins:make /home/piyush/ros_ws2/logs/rotors_gazebo_plugins/build.make.001.log                                                                                                
MagneticField.proto: warning: Import quaternion.proto but not used.
WindSpeedBeta.proto: warning: Import Header.proto but not used.
In file included from /opt/ros/melodic/include/mavlink/v2.0/ASLUAV/mavlink.h:32:0,
                 from /home/piyush/ros_ws2/src/rotors_simulator/rotors_gazebo_plugins/include/rotors_gazebo_plugins/gazebo_mavlink_interface.h:69,
                 from /home/piyush/ros_ws2/src/rotors_simulator/rotors_gazebo_plugins/src/gazebo_mavlink_interface.cpp:22:
/opt/ros/melodic/include/mavlink/v2.0/ASLUAV/ASLUAV.h:263:0: warning: "MAVLINK_MESSAGE_INFO" redefined
  #define MAVLINK_MESSAGE_INFO {MAVLINK_MESSAGE_INFO_HEARTBEAT, MAVLINK_MESSAGE_INFO_SYS_STATUS, MAVLINK_MESSAGE_INFO_SYSTEM_TIME, MAVLINK_MESSAGE_INFO_PING, MAVLINK_MESSAGE_INFO_CHANGE_OPERATOR_CONTROL, MAVLINK_MESSAGE_INFO_CHANGE_OPERATOR_CONTROL_ACK, MAVLINK_MESSAGE_INFO_AUTH_KEY, MAVLINK_MESSAGE_INFO_LINK_NODE_STATUS, MAVLINK_MESSAGE_INFO_SET_MODE, MAVLINK_MESSAGE_INFO_PARAM_REQUEST_READ, MAVLINK_MESSAGE_INFO_PARAM_REQUEST_LIST, MAVLINK_MESSAGE_INFO_PARAM_VALUE, MAVLINK_MESSAGE_INFO_PARAM_SET, MAVLINK_MESSAGE_INFO_GPS_RAW_INT, MAVLINK_MESSAGE_INFO_GPS_STATUS, MAVLINK_MESSAGE_INFO_SCALED_IMU, MAVLINK_MESSAGE_INFO_RAW_IMU, MAVLINK_MESSAGE_INFO_RAW_PRESSURE, MAVLINK_MESSAGE_INFO_SCALED_PRESSURE, MAVLINK_MESSAGE_INFO_ATTITUDE, MAVLINK_MESSAGE_INFO_ATTITUDE_QUATERNION, MAVLINK_MESSAGE_INFO_LOCAL_POSITION_NED, MAVLINK_MESSAGE_INFO_GLOBAL_POSITION_INT, MAVLINK_MESSAGE_INFO_RC_CHANNELS_SCALED, MAVLINK_MESSAGE_INFO_RC_CHANNELS_RAW, MAVLINK_MESSAGE_INFO_SERVO_OUTPUT_RAW, MAVLINK_MESSAGE_INFO_MISSION_REQUEST_PARTIAL_LIST, MAVLINK_MESSAGE_INFO_MISSION_WRITE_PARTIAL_LIST, MAVLINK_MESSAGE_INFO_MISSION_ITEM, MAVLINK_MESSAGE_INFO_MISSION_REQUEST, MAVLINK_MESSAGE_INFO_MISSION_SET_CURRENT, MAVLINK_MESSAGE_INFO_MISSION_CURRENT, MAVLINK_MESSAGE_INFO_MISSION_REQUEST_LIST, MAVLINK_MESSAGE_INFO_MISSION_COUNT, MAVLINK_MESSAGE_INFO_MISSION_CLEAR_ALL, MAVLINK_MESSAGE_INFO_MISSION_ITEM_REACHED, MAVLINK_MESSAGE_INFO_MISSION_ACK, MAVLINK_MESSAGE_INFO_SET_GPS_GLOBAL_ORIGIN, MAVLINK_MESSAGE_INFO_GPS_GLOBAL_ORIGIN, MAVLI....
 
 ### A lot of similar warnings were there and then a few errors appeared which were :
 INFO", 311 }, { "UAVCAN_NODE_STATUS", 310 }, { "UTM_GLOBAL_POSITION", 340 }, { "V2_EXTENSION", 248 }, { "VFR_HUD", 74 }, { "VIBRATION", 241 }, { "VICON_POSITION_ESTIMATE", 104 }, { "VIDEO_STREAM_INFORMATION", 269 }, { "VIDEO_STREAM_STATUS", 270 }, { "VISION_POSITION_ESTIMATE", 102 }, { "VISION_SPEED_ESTIMATE", 103 }, { "WHEEL_DISTANCE", 9000 }, { "WIFI_CONFIG_AP", 299 }, { "WIND_COV", 231 }}
 
/home/piyush/ros_ws2/src/rotors_simulator/rotors_gazebo_plugins/src/gazebo_mavlink_interface.cpp: In member function ‘void gazebo::GazeboMavlinkInterface::VaneCallback(gazebo::VanePtr&)’:
/home/piyush/ros_ws2/src/rotors_simulator/rotors_gazebo_plugins/src/gazebo_mavlink_interface.cpp:988:3: error: ‘mavlink_hil_extended_t’ was not declared in this scope
   mavlink_hil_extended_t hil_extended_msg;
   ^~~~~~~~~~~~~~~~~~~~~~
/home/piyush/ros_ws2/src/rotors_simulator/rotors_gazebo_plugins/src/gazebo_mavlink_interface.cpp:988:3: note: suggested alternative: ‘mavlink_hil_sensor_t’
   mavlink_hil_extended_t hil_extended_msg;
   ^~~~~~~~~~~~~~~~~~~~~~
   mavlink_hil_sensor_t
/home/piyush/ros_ws2/src/rotors_simulator/rotors_gazebo_plugins/src/gazebo_mavlink_interface.cpp:991:3: error: ‘hil_extended_msg’ was not declared in this scope
   hil_extended_msg.timestamp = world_->SimTime().Double() * 1e6;
   ^~~~~~~~~~~~~~~~
/home/piyush/ros_ws2/src/rotors_simulator/rotors_gazebo_plugins/src/gazebo_mavlink_interface.cpp:1006:3: error: ‘mavlink_msg_hil_extended_encode_chan’ was not declared in this scope
   mavlink_msg_hil_extended_encode_chan(1, 200, MAVLINK_COMM_0, &msg, &hil_extended_msg);
   ^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
/home/piyush/ros_ws2/src/rotors_simulator/rotors_gazebo_plugins/src/gazebo_mavlink_interface.cpp:1006:3: note: suggested alternative: ‘mavlink_msg_hil_sensor_encode_chan’
   mavlink_msg_hil_extended_encode_chan(1, 200, MAVLINK_COMM_0, &msg, &hil_extended_msg);
   ^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
   mavlink_msg_hil_sensor_encode_chan
make[2]: *** [CMakeFiles/rotors_gazebo_mavlink_interface.dir/src/gazebo_mavlink_interface.cpp.o] Error 1
make[2]: *** Waiting for unfinished jobs....
make[1]: *** [CMakeFiles/rotors_gazebo_mavlink_interface.dir/all] Error 2
make[1]: *** Waiting for unfinished jobs....
make: *** [all] Error 2

## Solution:
1. In CMakeLists.txt, I commented the lines from 431 to 441(putting '#' before the line comments the sentence in this language) which were : 

 Note that this library includes TWO .cpp files.
    add_library(rotors_gazebo_mavlink_interface SHARED src/gazebo_mavlink_interface.cpp src/geo_mag_declination_tmp.cpp)
    target_link_libraries(rotors_gazebo_mavlink_interface ${target_linking_LIBRARIES}  ${mav_msgs})
    add_dependencies(rotors_gazebo_mavlink_interface ${catkin_EXPORTED_TARGETS} ${mavros_EXPORTED_TARGETS} ${mavros_msgs_EXPORTED_TARGETS})
    list(APPEND targets_to_install rotors_gazebo_mavlink_interface)

    Note that this library includes TWO .cpp files.
    add_library(rotors_gazebo_mavlink_interface_tmp SHARED src/gazebo_mavlink_interface_tmp.cpp src/geo_mag_declination_tmp.cpp)
    target_link_libraries(rotors_gazebo_mavlink_interface_tmp ${target_linking_LIBRARIES}  ${mav_msgs})
    add_dependencies(rotors_gazebo_mavlink_interface_tmp ${catkin_EXPORTED_TARGETS} ${mavros_EXPORTED_TARGETS} ${mavros_msgs_EXPORTED_TARGETS})
    list(APPEND targets_to_install rotors_gazebo_mavlink_interface_tmp)
   
   I'll add the reason for the same later.
 2. In gazebo_wind_beta_plugin.cpp, a new line was added `using namespace std::complex_literals;` because errors related to complex numbers were also coming.
 
 And then I was able to build the same:)
 
 
# 2. Resolving errors while building Offboard (Map_generation repo)
 
 
 Errors     << Offboard:make /home/piyush/ros_ws/logs/Offboard/build.make.006.log                                                                                                             
/home/piyush/ros_ws/src/Offboard/src/node1.cpp:1:10: fatal error: Offboard/node1.hpp: No such file or directory
 #include <Offboard/node1.hpp>
          ^~~~~~~~~~~~~~~~~~~~
compilation terminated.
make[2]: *** [CMakeFiles/rosco_node.dir/src/node1.cpp.o] Error 1
make[1]: *** [CMakeFiles/rosco_node.dir/all] Error 2
make: *** [all] Error 2
cd /home/piyush/ros_ws/build/Offboard; catkin build --get-env Offboard | catkin env -si  /usr/bin/make --jobserver-fds=6,7 -j; cd -


### Situation:

Initially there was no include directory and hence no hpp files. After making an include directory and hence hpp files, I got this error.

## Solution:

`include_directories(include ${catkin_INCLUDE_DIRS})` 

this needs to be added in CMakeLists.txt after 

`find_package(catkin REQUIRED COMPONENTS ...)` 

so that the cpp file can track the includePath.
