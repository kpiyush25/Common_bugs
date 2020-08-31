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
