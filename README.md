# suboptimax
minmax planner for suboptimal explanations - Explainable Agency by Revealing Suboptimality in CHRI Learning Scenarios

##ROS config
Install ROS melodic and catkin following this link: https://wiki.ros.org/catkin#Installing_catkin

Clone the repository
$ git clone https://github.com/Silviatulli/suboptimax.git
Remember to make the python files executable by running the following command for each script:

$ chmod +x filename.py
Build a catkin workspace and source the setup file run:

$ cd ~/catkin_ws
$ catkin_make
add the workspace to the ROS environment:

$. ~/catkin_ws/devel/setup.bash
Make sure that the CMakeLists.txt file is configured properly, with all the services and the dependencies listed as follows:

find_package(catkin REQUIRED COMPONENTS roscpp rospy std_msgs message_generation message_runtime )
add_service_files( FILES Decision.srv GameState.srv Plan.srv RobotExplanation.srv RobotTalk.srv )
If you work with the NAO Robot uncomment the line 7, from 41 to 65 and 85 (self.robot_communication.say(self.explanation_text)) in the file robot_manager.py. Create a folder sdk that contains the pynaoqi sdk required and modify your bashrc ($gedit ~/.bashrc) to indicate the python and library path as following:

export PYTHONPATH=$PYTHONPATH:~/sdk/pynaoqi-python2.7-2.1.2.17-linux64
export LD_LIBRARY_PATH=${LD_LIBRARY_PATH}:/home/<your_pc_name>/sdk/pynaoqi-python2.7-2.1.2.17-linux64
you can download the pynaoqi sdk following this guide: http://wiki.ros.org/nao/Tutorials/Installation

Launch the code:

open a terminal and launch: $ roscore
open a second terminal into your repository folder and launch minmax.launch: $ roslaunch minmax.launch
if you have any doubts please do not hesitate to contact me by e-mail
