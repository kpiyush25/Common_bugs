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
### (Branch was hil_interface, everything was fine on master)

CMake Error at /home/piyush/ros_ws2/src/rotors_simulator/rotors_gazebo_plugins/CMakeLists.txt:96 (target_link_libraries):
  Error evaluating generator expression:

    $<TARGET_PROPERTY:UUID::UUID,INTERFACE_INCLUDE_DIRECTORIES>

  Target "UUID::UUID" not found.


CMake Error:
  Error evaluating generator expression:

    $<TARGET_PROPERTY:UUID::UUID,INTERFACE_INCLUDE_DIRECTORIES>

  Target "UUID::UUID" not found.


CMake Error:
  Error evaluating generator expression:

    $<TARGET_PROPERTY:UUID::UUID,INTERFACE_INCLUDE_DIRECTORIES>

  Target "UUID::UUID" not found.


CMake Error at /home/piyush/ros_ws2/src/rotors_simulator/rotors_gazebo_plugins/CMakeLists.txt:96 (target_link_libraries):
  Error evaluating generator expression:

    $<TARGET_PROPERTY:UUID::UUID,INTERFACE_INCLUDE_DIRECTORIES>

  Target "UUID::UUID" not found.


CMake Error at /home/piyush/ros_ws2/src/rotors_simulator/rotors_gazebo_plugins/CMakeLists.txt:92 (target_link_libraries):
  Error evaluating generator expression:

    $<TARGET_PROPERTY:UUID::UUID,INTERFACE_INCLUDE_DIRECTORIES>

  Target "UUID::UUID" not found.


CMake Error:
  Error evaluating generator expression:

    $<TARGET_PROPERTY:UUID::UUID,INTERFACE_INCLUDE_DIRECTORIES>

  Target "UUID::UUID" not found.


CMake Error:
  Error evaluating generator expression:

    $<TARGET_PROPERTY:UUID::UUID,INTERFACE_INCLUDE_DIRECTORIES>

  Target "UUID::UUID" not found.


CMake Error at /home/piyush/ros_ws2/src/rotors_simulator/rotors_gazebo_plugins/CMakeLists.txt:92 (target_link_libraries):
  Error evaluating generator expression:

    $<TARGET_PROPERTY:UUID::UUID,INTERFACE_INCLUDE_DIRECTORIES>

  Target "UUID::UUID" not found.


CMake Error at /home/piyush/ros_ws2/src/rotors_simulator/rotors_gazebo_plugins/CMakeLists.txt:80 (target_link_libraries):
  Error evaluating generator expression:

    $<TARGET_PROPERTY:UUID::UUID,INTERFACE_INCLUDE_DIRECTORIES>

  Target "UUID::UUID" not found.


CMake Error:
  Error evaluating generator expression:

    $<TARGET_PROPERTY:UUID::UUID,INTERFACE_INCLUDE_DIRECTORIES>

  Target "UUID::UUID" not found.

then similar errors like this were there and then a few warnings and then different errors which were as below:
In file included from /home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/include/rotors_hil_interface/hil_interface.h:25:0,
                 from /home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_sensor_level_interface.cpp:17:
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/include/rotors_hil_interface/hil_listeners.h:143:77: note:   cannot convert ‘rotors_hil::kMetersToCm_cm_per_m’ (type ‘const float’) to type ‘const StorageBaseType& {aka const Eigen::MatrixBase<Eigen::Matrix<int, 3, 1> >&}’
                                         ground_speed_msg->twist.linear.z) * kMetersToCm_cm_per_m;
                                                                             ^~~~~~~~~~~~~~~~~~~~
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/include/rotors_hil_interface/hil_listeners.h: In member function ‘void rotors_hil::HilListeners::PressureCallback(const FluidPressureConstPtr&, rotors_hil::HilData*)’:
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/include/rotors_hil_interface/hil_listeners.h:201:15: error: ‘struct rotors_hil::HilData’ has no member named ‘pressure_abs’; did you mean ‘pressure_alt_m’?
     hil_data->pressure_abs = pressure_mbar;
               ^~~~~~~~~~~~
               pressure_alt_m
In file included from /home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_sensor_level_interface.cpp:17:0:
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/include/rotors_hil_interface/hil_interface.h: At global scope:
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/include/rotors_hil_interface/hil_interface.h:105:3: error: ‘mavlink_hil_gps_t’ does not name a type; did you mean ‘mavlink_ck_a’?
   mavlink_hil_gps_t hil_gps_msg_;
   ^~~~~~~~~~~~~~~~~
   mavlink_ck_a
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/include/rotors_hil_interface/hil_interface.h:108:3: error: ‘mavlink_hil_sensor_t’ does not name a type
   mavlink_hil_sensor_t hil_sensor_msg_;
   ^~~~~~~~~~~~~~~~~~~~
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/include/rotors_hil_interface/hil_interface.h:130:3: error: ‘mavlink_hil_state_quaternion_t’ does not name a type; did you mean ‘mavlink_dcm_to_quaternion’?
   mavlink_hil_state_quaternion_t hil_state_qtrn_msg_;
   ^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
   mavlink_dcm_to_quaternion
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_sensor_level_interface.cpp: In member function ‘virtual std::vector<mavros_msgs::Mavlink_<std::allocator<void> > > rotors_hil::HilSensorLevelInterface::CollectData()’:
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_sensor_level_interface.cpp:89:3: error: ‘mavlink_message_t’ was not declared in this scope
   mavlink_message_t mmsg;
   ^~~~~~~~~~~~~~~~~
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_sensor_level_interface.cpp:89:3: note: suggested alternatives:
In file included from /opt/ros/melodic/include/mavlink/v2.0/common/../message.hpp:16:0,
                 from /opt/ros/melodic/include/mavlink/v2.0/common/common.hpp:16,
                 from /opt/ros/melodic/include/mavconn/mavlink_dialect.h:26,
                 from /opt/ros/melodic/include/mavros_msgs/mavlink_convert.h:18,
                 from /home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/include/rotors_hil_interface/hil_interface.h:23,
                 from /home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_sensor_level_interface.cpp:17:
/opt/ros/melodic/include/mavlink/v2.0/common/../mavlink_types.h:121:4: note:   ‘mavlink::mavlink_message_t’
 }) mavlink_message_t;
    ^~~~~~~~~~~~~~~~~
/opt/ros/melodic/include/mavlink/v2.0/common/../mavlink_types.h:121:4: note:   ‘mavlink::mavlink_message_t’
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_sensor_level_interface.cpp:105:5: error: ‘hil_gps_msg_’ was not declared in this scope
     hil_gps_msg_.time_usec = time_usec;
     ^~~~~~~~~~~~
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_sensor_level_interface.cpp:105:5: note: suggested alternative: ‘hil_msgs’
     hil_gps_msg_.time_usec = time_usec;
     ^~~~~~~~~~~~
     hil_msgs
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_sensor_level_interface.cpp:119:5: error: ‘mavlink_hil_gps_t’ was not declared in this scope
     mavlink_hil_gps_t* hil_gps_msg_ptr = &hil_gps_msg_;
     ^~~~~~~~~~~~~~~~~
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_sensor_level_interface.cpp:119:5: note: suggested alternative: ‘mavlink_ck_a’
     mavlink_hil_gps_t* hil_gps_msg_ptr = &hil_gps_msg_;
     ^~~~~~~~~~~~~~~~~
     mavlink_ck_a
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_sensor_level_interface.cpp:119:24: error: ‘hil_gps_msg_ptr’ was not declared in this scope
     mavlink_hil_gps_t* hil_gps_msg_ptr = &hil_gps_msg_;
                        ^~~~~~~~~~~~~~~
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_sensor_level_interface.cpp:120:39: error: ‘mmsg’ was not declared in this scope
     mavlink_msg_hil_gps_encode(1, 0, &mmsg, hil_gps_msg_ptr);
                                       ^~~~
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_sensor_level_interface.cpp:120:39: note: suggested alternative: ‘mag’
     mavlink_msg_hil_gps_encode(1, 0, &mmsg, hil_gps_msg_ptr);
                                       ^~~~
                                       mag
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_sensor_level_interface.cpp:120:5: error: ‘mavlink_msg_hil_gps_encode’ was not declared in this scope
     mavlink_msg_hil_gps_encode(1, 0, &mmsg, hil_gps_msg_ptr);
     ^~~~~~~~~~~~~~~~~~~~~~~~~~
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_sensor_level_interface.cpp:131:3: error: ‘hil_sensor_msg_’ was not declared in this scope
   hil_sensor_msg_.time_usec = time_usec;
   ^~~~~~~~~~~~~~~
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_sensor_level_interface.cpp:147:3: error: ‘mavlink_hil_sensor_t’ was not declared in this scope
   mavlink_hil_sensor_t* hil_sensor_msg_ptr = &hil_sensor_msg_;
   ^~~~~~~~~~~~~~~~~~~~
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_sensor_level_interface.cpp:147:25: error: ‘hil_sensor_msg_ptr’ was not declared in this scope
   mavlink_hil_sensor_t* hil_sensor_msg_ptr = &hil_sensor_msg_;
                         ^~~~~~~~~~~~~~~~~~
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_sensor_level_interface.cpp:148:40: error: ‘mmsg’ was not declared in this scope
   mavlink_msg_hil_sensor_encode(1, 0, &mmsg, hil_sensor_msg_ptr);
                                        ^~~~
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_sensor_level_interface.cpp:148:40: note: suggested alternative: ‘mag’
   mavlink_msg_hil_sensor_encode(1, 0, &mmsg, hil_sensor_msg_ptr);
                                        ^~~~
                                        mag
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_sensor_level_interface.cpp:148:3: error: ‘mavlink_msg_hil_sensor_encode’ was not declared in this scope
   mavlink_msg_hil_sensor_encode(1, 0, &mmsg, hil_sensor_msg_ptr);
   ^~~~~~~~~~~~~~~~~~~~~~~~~~~~~
make[2]: *** [CMakeFiles/rotors_hil_interface.dir/src/hil_sensor_level_interface.cpp.o] Error 1
make[2]: *** Waiting for unfinished jobs....
In file included from /home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/include/rotors_hil_interface/hil_interface.h:25:0,
                 from /home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_state_level_interface.cpp:17:
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/include/rotors_hil_interface/hil_listeners.h: In member function ‘void rotors_hil::HilListeners::GroundSpeedCallback(const TwistStampedConstPtr&, rotors_hil::HilData*)’:
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/include/rotors_hil_interface/hil_listeners.h:143:75: error: no match for ‘operator*’ (operand types are ‘Eigen::Vector3i {aka Eigen::Matrix<int, 3, 1>}’ and ‘const float’)
     hil_data->gps_vel_cm_per_s = Eigen::Vector3i(ground_speed_msg->twist.linear.x,
                                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
                                         ground_speed_msg->twist.linear.y,
                                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~  
                                         ground_speed_msg->twist.linear.z) * kMetersToCm_cm_per_m;
                                         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
  
  
  These were the errors in the last:
     ^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
   mavlink_dcm_to_quaternion
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_state_level_interface.cpp:102:35: error: ‘hil_state_qtrn_msg_ptr’ was not declared in this scope
   mavlink_hil_state_quaternion_t* hil_state_qtrn_msg_ptr = &hil_state_qtrn_msg_;
                                   ^~~~~~~~~~~~~~~~~~~~~~
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_state_level_interface.cpp:103:50: error: ‘mmsg’ was not declared in this scope
   mavlink_msg_hil_state_quaternion_encode(1, 0, &mmsg, hil_state_qtrn_msg_ptr);
                                                  ^~~~
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_state_level_interface.cpp:103:3: error: ‘mavlink_msg_hil_state_quaternion_encode’ was not declared in this scope
   mavlink_msg_hil_state_quaternion_encode(1, 0, &mmsg, hil_state_qtrn_msg_ptr);
   ^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
/home/piyush/ros_ws2/src/rotors_simulator/rotors_hil_interface/src/hil_state_level_interface.cpp:103:3: note: suggested alternative: ‘mavlink_dcm_to_quaternion’
   mavlink_msg_hil_state_quaternion_encode(1, 0, &mmsg, hil_state_qtrn_msg_ptr);
   ^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
   mavlink_dcm_to_quaternion
make[2]: *** [CMakeFiles/rotors_hil_interface.dir/src/hil_state_level_interface.cpp.o] Error 1
make[1]: *** [CMakeFiles/rotors_hil_interface.dir/all] Error 2
make: *** [all] Error 2
cd /home/piyush/ros_ws2/build/rotors_hil_interface; catkin build --get-env rotors_hil_interface | catkin env -si  /usr/bin/make --jobserver-fds=6,7 -j; cd -
...........................................................................................................................................................................................................
Failed     << rotors_hil_interface:make            [ Exited with code 2 ]                                                                                                                                  
Failed    <<< rotors_hil_interface                 [ 7.7 seconds ]       

## Still finding!
