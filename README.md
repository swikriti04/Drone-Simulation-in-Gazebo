# Drone-Simulation-in-Gazebo

## 1. Quick Start
The project is developed and tested in Ubuntu 16.04, ROS Kinetic. Run the following commands to setup:
 sudo apt-get install libnlopt-dev libarmadillo-dev
 cd ${YOUR_WORKSPACE_PATH}/src
 git clone https://github.com/HKUST-Aerial-Robotics/Fast-Planner.git
 cd ../
 catkin_make
 
After compilation you can start the visualization by:
source devel/setup.bash
roslaunch plan_manage rviz.launch 

and start a simulation (run in a new terminals):
source devel/setup.bash
roslaunch plan_manage kino_replan.launch

You will find the random map and the drone in Rviz. You can select goals for the drone to reach using the 2D Nav Goal tool. A sample simulation is showed here.

## 2. Setup and Config
The uav_simulator depends on the C++ linear algebra library Armadillo. The two dependencies can be installed by
sudo apt-get install libnlopt-dev libarmadillo-dev 

Build on ROS
After the prerequisites are satisfied, you can clone this repository to your catkin workspace and catkin_make. A new workspace is recommended:

  cd ${YOUR_WORKSPACE_PATH}/src
  git clone https://github.com/HKUST-Aerial-Robotics/Fast-Planner.git
  cd ../
  catkin_make
  
## 3. Run Simulations
Run Rviz with our configuration firstly:

  <!-- go to your workspace and run: -->
  source devel/setup.bash
  roslaunch plan_manage rviz.launch
Then run the quadrotor simulator and Fast-Planner. Several examples are provided below:

Kinodynamic Path Searching & B-spline Optimization
In this method, a kinodynamic path searching finds a safe, dynamically feasible, and minimum-time initial trajectory in the discretized control space. Then the smoothness and clearance of the trajectory are improved by a B-spline optimization. To test this method, run:

  <!-- open a new terminal, go to your workspace and run: -->
  source devel/setup.bash
  roslaunch plan_manage kino_replan.launch
Normally, you will find the randomly generated map and the drone model in Rviz. At this time, you can trigger the planner using the 2D Nav Goal tool. When a point is clicked in Rviz, a new trajectory will be generated immediately and executed by the drone. A sample is displayed below:
