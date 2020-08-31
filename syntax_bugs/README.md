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


###just a testing ..I'll delete this line soon
