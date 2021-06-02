## Explainable Agency by Revealing Suboptimalityin Child-Robot Learning Scenarios
Revealing the internal workings of a robot can help a human better understand the robot's behaviors. How to reveal such workings, e.g., via explanation generation, remains a significant challenge. This gets even more complex when these explanations are targeted towards children.
Therefore, we propose a search-based approach to generate contrastive explanations using optimal and sub-optimal plans and implement it in a scenario for children. In the application scenario, the child and the robot learn together how to play a zero-sum game that requires logical and mathematical thinking.
We report results around our explanation generation system that was successfully deployed among seven-year-old children. Our results show trends that the generated explanations were able to positively affect the children's perceived difficulty in learning the zero-sum game.

For additional details about the research work you can check out our paper: [Explainable Agency by Revealing Suboptimalityin Child-Robot Learning Scenarios](https://link.springer.com/chapter/10.1007/978-3-030-62056-1_3)

## Test
To run the code:
- open a terminal and launch: $ roscore
- open a second terminal into your repository folder and launch minmax.launch: $ roslaunch minmax.launch

## Config
- **Install [ROS melodic](http://wiki.ros.org/melodic) and [catkin](https://wiki.ros.org/catkin#Installing_catkin)**

- **Clone the repository**
   - $ git clone https://github.com/Silviatulli/suboptimax.git

- **Make the python files executable** 
 Run the following command for each script:
 - $ chmod +x filename.py

- **Build a catkin workspace and source the setup file**
  - $ cd ~/catkin_ws
  - $ catkin_make

- **Add the workspace to the ROS environment**
  - $. ~/catkin_ws/devel/setup.bash

- **Make sure that the CMakeLists.txt file is configured properly** 
- All the services and the dependencies should be as follows:
  - find_package (catkin REQUIRED COMPONENTS roscpp rospy std_msgs message_generation message_runtime )
  - add_service_files (FILES Decision.srv GameState.srv Plan.srv RobotExplanation.srv RobotTalk.srv )

- **Make it work with the Robot**
- If you work with the NAO Robot uncomment the line 7, from 41 to 65 and 85 (self.robot_communication.say(self.explanation_text)) in the file robot_manager.py. 
- Create a folder sdk that contains the pynaoqi sdk required and modify your bashrc ($gedit ~/.bashrc) to indicate the python and library paths as follows:
  - export PYTHONPATH=$PYTHONPATH:~/sdk/pynaoqi-python2.7-2.1.2.17-linux64
  - export LD_LIBRARY_PATH=${LD_LIBRARY_PATH}:/home/<your_pc_name>/sdk/pynaoqi-python2.7-2.1.2.17-linux64
  - you can download the pynaoqi sdk following this [guide](http://wiki.ros.org/nao/Tutorials/Installation)
