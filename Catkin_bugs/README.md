
Skip to content
Pull requests
Issues
Marketplace
Explore
@kpiyush25
kpiyush25 /
Common_bugs
Private

1
0

    0

Code
Issues 1
Pull requests
Actions
Projects
Wiki
Security
Insights

    Settings

Common_bugs/Catkin_bugs
@kpiyush25
kpiyush25 Create Catkin_bugs
Latest commit 52e0b5b now
History
1 contributor
63 lines (59 sloc) 3.6 KB
piyush@piyush-Nitro-AN515-54:~/planning_ws/src$ catkin init
Initializing catkin workspace in `/home/piyush/planning_ws/src`.
--------------------------------------------------------------------------------
Profile:                     default
Extending:             [env] /home/piyush/drdo_ws/devel:/home/piyush/rosflight_ws/devel:/home/piyush/ros_ws3/devel:/home/piyush/iarc_ws/devel:/home/piyush/catkin_ws/devel:/home/piyush/ros_ws2/devel:/opt/ros/melodic
Workspace:                   /home/piyush/planning_ws/src
--------------------------------------------------------------------------------
Build Space:       [missing] /home/piyush/planning_ws/src/build
Devel Space:       [missing] /home/piyush/planning_ws/src/devel
Install Space:      [unused] /home/piyush/planning_ws/src/install
Log Space:         [missing] /home/piyush/planning_ws/src/logs
Source Space:      [missing] /home/piyush/planning_ws/src/src
DESTDIR:            [unused] None
--------------------------------------------------------------------------------
Devel Space Layout:          linked
Install Space Layout:        None
--------------------------------------------------------------------------------
Additional CMake Args:       None
Additional Make Args:        None
Additional catkin Make Args: None
Internal Make Job Server:    True
Cache Job Environments:      False
--------------------------------------------------------------------------------
Whitelisted Packages:        None
Blacklisted Packages:        None
--------------------------------------------------------------------------------


--------------------------------------------------------------------------------
WARNING: Source space `/home/piyush/planning_ws/src/src` does not yet exist.
--------------------------------------------------------------------------------

Issue: This came because I did ```catkin init``` after going inside src but it needed to be 
needed to be done inside the workspace but outside the src. The actual output looks like following:

piyush@piyush-Nitro-AN515-54:~/planning_ws$ catkin init
Initializing catkin workspace in `/home/piyush/planning_ws`.
--------------------------------------------------------------------------------
Profile:                     default
Extending:             [env] /home/piyush/drdo_ws/devel:/home/piyush/rosflight_ws/devel:/home/piyush/ros_ws3/devel:/home/piyush/iarc_ws/devel:/home/piyush/catkin_ws/devel:/home/piyush/ros_ws2/devel:/opt/ros/melodic
Workspace:                   /home/piyush/planning_ws
--------------------------------------------------------------------------------
Build Space:       [missing] /home/piyush/planning_ws/build
Devel Space:       [missing] /home/piyush/planning_ws/devel
Install Space:      [unused] /home/piyush/planning_ws/install
Log Space:         [missing] /home/piyush/planning_ws/logs
Source Space:       [exists] /home/piyush/planning_ws/src
DESTDIR:            [unused] None
--------------------------------------------------------------------------------
Devel Space Layout:          linked
Install Space Layout:        None
--------------------------------------------------------------------------------
Additional CMake Args:       None
Additional Make Args:        None
Additional catkin Make Args: None
Internal Make Job Server:    True
Cache Job Environments:      False
--------------------------------------------------------------------------------
Whitelisted Packages:        None
Blacklisted Packages:        None
--------------------------------------------------------------------------------
Workspace configuration appears valid.
--------------------------------------------------------------------------------

    © 2021 GitHub, Inc.
    Terms
    Privacy
    Security
    Status
    Docs

    Contact GitHub
    Pricing
    API
    Training
    Blog
    About

Loading complete
