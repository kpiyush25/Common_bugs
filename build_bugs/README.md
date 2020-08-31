# Resolving errors while building iars_simulation_tools
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


