First create a catkin workspace in your system.
In the catkin workspace clone the PX4 source code: git clone https://github.com/PX4/PX4-Autopilot.git --recursive
Run the ubuntu.sh with no arguments (in a bash shell) to install everything:bash ./PX4-Autopilot/Tools/setup/ubuntu.sh
Restart the computer on completion.
Creating the ROS Package:
Open the terminal and go to ~/catkin_ws/src directory.
In the ~/catkin_ws/src directory create a new package named offboard_py (in this case) with the rospy dependency:catkin_create_pkg offboard_py rospy
Build the new package in the ~/catkin_ws/ directory:
cd .. # Assuming previous directory to be ~/catkin_ws/src
catkin build
source devel/setup.bash
You should now be able to cd into the package by using:roscd offboard_py
To store your Python files, create a new folder called /scripts on the package:
mkdir scripts
cd scripts
In the scripts folder copy the following files:random_path4.py,data_saver_1.py and path.py
create roslaunch file:
roscd offboard_py
mkdir launch
cd launch
touch start_offb.launch
In the start_offb.launch file copy and paste the code from start_offb.launch file of the repository.
Now in one terminal run : roslaunch offboard_py start_offb.launch
In another terminal go scripts file directory and run :python3 path.py and in another terminal run rviz and add path topic there to visualize the path.
Similarly in another topic run data_saver_1.py to save the data in csv file.
