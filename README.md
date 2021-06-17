# Multi-Turtlebot Simulation Exploration based on RRT
This package is a compilation of the RRT package in a much complete package rather than figuring map merging and other function from other resipotary. 
This would serve as a self-contained package for the exploration module using simulation for the turtlebot.


credit to hasauino for creating the RRT exploration packages.

[RRT Exploration package](https://github.com/hasauino/rrt_exploration "RRT Exploration").

[RRT Exploration Tutorial package](https://github.com/hasauino/rrt_exploration_tutorials "RRT Exploration").


## Requirements
The following code is exectuted in ROS Kinetic in Ubuntu 16.04 LTS

The following libraries are required to install before proceeding to run the code

    $ sudo apt-get install ros-kinetic-gmapping
    $ sudo apt-get install ros-kinetic-navigation
    $ sudo apt-get install ros-kinetic-kobuki ros-kinetic-kobuki-core
    $ sudo apt-get install ros-kinetic-kobuki-gazebo
    $ sudo apt-get install python-opencv
    $ sudo apt-get install python-numpy
    $ sudo apt-get install python-scikits-learn


## Installation Process
create a new folder called "catkin_explore/src" by executing the following comment:

    $ sudo mkdir -p ~/catkin_explore/src
    $ cd ~/catkin_explore/src/
    $ git clone https://github.com/hikashi/multi-robot-explore.git
    $ cd ~/catkin_explore
    $ catkin_make


## Execution
The program can be executed using the following comments in three terminal:

Terminal 1

     # roscore 
Terminal 2

     # source ~/catkin_explore/devel/setup.bash 
     # roslaunch rrt_exploration_tutorials mutliple_simulated_largeMap.launch 
Terminal 3

     # source ~/catkin_explore/devel/setup.bash 
     # roslaunch rrt_exploration three_robots.launch 

## Exploration Process
The exploration relies on the correct sequence else rendering with no goal for each of the robot.
1. Top Left
2. Bottom Left
3. Bottom Right
4. Top Right
5. Initial Point

As shown in the following figure for the sequence:
 ![Instruction](/instruction2.png)

## Error with library issues
If you encountered issues such as:

    ERROR: cannot launch node of type [rrt_exploration/filter.py]: can't locate node [filter.py] in package [rrt_exploration]
    ERROR: cannot launch node of type [rrt_exploration/assigner.py]: can't locate node [assigner.py] in package [rrt_exploration]

You may need to change the file permission to executable using the following commands:

    chmod +x ~/[YOUR_DIRECTORY]/src/multi-robot-explore/rrt_exploration/scripts/filter.py 
    chmod +x ~/[YOUR_DIRECTORY]/src/multi-robot-explore/rrt_exploration/scripts/assigner.py 


## Known issues
- Tasks allocation for each of the robots is very limited
- Expandability of the robots. (Currently 1 or 3 robots)
- Stucked locally (maybe the collision avoidance / path planning not so optimal)
- Exploration ended before whole map is being explored. 
