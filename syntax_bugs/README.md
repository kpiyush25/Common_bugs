## Error1
Errors  << dubins_trajectory_generator:make /home/piyush/iarc_ws/logs/dubins_trajectory_generator/build.make.026.log
In file included from /home/piyush/iarc_ws/src/IARC2020/iarc_trajectory_estimation/dubins_trajectory_generator/src/dubins_trajectory.cpp:1:0:
/home/piyush/iarc_ws/src/IARC2020/iarc_trajectory_estimation/dubins_trajectory_generator/include/dubins_trajectory_generator/dubins_trajectory.hpp:48:10:
error: default argument missing for parameter 5 of ‘void ariitk::trajectory_generation::DubinsTrajectory::visualizeTrajectory(const string&, 
std::vector<ariitk::trajectory_generation::Point>, const string&, const ariitk::trajectory_generation::DubinsTrajectory::ColorType&, const double&)’
    void visualizeTrajectory(const std::string& topic_name, std::vector<Point> trajectory,
          ^~~~~~~~~~~~~~~~~~~
make[2]: *** [CMakeFiles/dubins_trajectory_generator.dir/src/dubins_trajectory.cpp.o] Error 1
make[1]: *** [CMakeFiles/dubins_trajectory_generator.dir/all] Error 2
make: *** [all] Error 2

### Solution: 
You can't have non-default parameters after your default parameters begin.
### Changes: 
          void visualizeTrajectory(const std::string& topic_name, std::vector<Point> trajectory, const std::string& frame_id = "world",
                                        const ColorType& color = ColorType::PINK, const double& size_factor);
                                                  
                                                                 to
                                                                                              
         void visualizeTrajectory(const std::string& topic_name, std::vector<Point> trajectory,
                                       const std::string& frame_id = "world", const ColorType& color = ColorType::PINK, const double& size_factor= 0.5);




## Error2
Errors     << dubins_trajectory_generator:make /home/piyush/iarc_ws/logs/dubins_trajectory_generator/build.make.005.log
/home/piyush/iarc_ws/src/IARC2020/iarc_trajectory_estimation/dubins_trajectory_generator/src/dubins_trajectory.cpp: In member function ‘void ariitk::trajectory_generation::DubinsTrajectory::generateTrajectory()’:
/home/piyush/iarc_ws/src/IARC2020/iarc_trajectory_estimation/dubins_trajectory_generator/src/dubins_trajectory.cpp:333:44: error: ‘visualization_msgs::MarkerArray {aka struct visualization_msgs::MarkerArray_<std::allocator<void> >}’ has no member named ‘size’
     for (uint i = 0; i < starting_markers_.size(); i++) {
                                            ^~~~
/home/piyush/iarc_ws/src/IARC2020/iarc_trajectory_estimation/dubins_trajectory_generator/src/dubins_trajectory.cpp:335:30: error: ‘visualization_msgs::MarkerArray {aka struct visualization_msgs::MarkerArray_<std::allocator<void> >}’ has no member named ‘push_back’
             starting_markers.push_back(starting_markers_[i]);
                              ^~~~~~~~~
/home/piyush/iarc_ws/src/IARC2020/iarc_trajectory_estimation/dubins_trajectory_generator/src/dubins_trajectory.cpp:335:57: error: no match for ‘operator[]’ (operand types are ‘visualization_msgs::MarkerArray {aka visualization_msgs::MarkerArray_<std::allocator<void> >}’ and ‘uint {aka unsigned int}’)
             starting_markers.push_back(starting_markers_[i]);
                                                         ^
/home/piyush/iarc_ws/src/IARC2020/iarc_trajectory_estimation/dubins_trajectory_generator/src/dubins_trajectory.cpp:338:23: error: ‘visualization_msgs::MarkerArray {aka struct visualization_msgs::MarkerArray_<std::allocator<void> >}’ has no member named ‘clear’
     starting_markers_.clear();

### Solution:
To know the size of the visualisation_msgs MarkerArray you have to specify that you want to know the size of the markers which is basically it's subfield.
### Changes
for (uint i = 0; i < starting_markers_.size(); i++) {

        if (i % 4 == 0) {
        
            starting_markers.push_back(starting_markers_[i]);
            
        }
        
 }
 
 starting_markers_.clear();
 
                                            to 
                                            
`for (uint i = 0; i < starting_markers_.markers.size(); i++) {

        if (i % 4 == 0) {
        
            starting_markers.markers.push_back(starting_markers_.markers[i]);
            
        }
        
 }
 
 starting_markers_.markers.clear();`
    
