tar file ko extract krke gazebo install kiya tha...so jab terminal se remove kr rhe the
so that new version of gazebo can be installed to remove krne ke baad bhi dikha rha tha version check krne pe..
so the following steps were done:
mkdir build
cd build
cmake ..
make uninstall
make
make -j6
sudo make install
sudo make uninstall
sudo apt-get install ros-melodic-desktop-full
phir rotors and iarc_sim ko clean krke build kiya finally launch file kaam krne
