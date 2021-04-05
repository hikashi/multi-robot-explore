# Multi-Turtlebot Simulation Exploration based on RRT
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
    $ git clone git@github.com:hikashi/multi-robot-explore.git
    $ cd ~/catkin_explore
    $ catkin_make


## Execution
The program can be executed using the following comments in three terminal:
Terminal 1

     # roscore 
Terminal 2

     # . ~/catkin_explore/devel/setup.bash 
     # roslaunch rrt_exploration_tutorials mutliple_simulated_largeMap.launch 
Terminal 3

     # . ~/catkin_explore/devel/setup.bash 
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


## Known issues
- Tasks allocation for each of the robots is very limited
- Expandability of the robots. (Currently 1 or 3 robots)
- Stucked locally (maybe the collision avoidance / path planning not so optimal)
- Exploration ended before whole map is being explored. 
