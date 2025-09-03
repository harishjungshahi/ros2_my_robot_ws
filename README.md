ROS2 My Robot Workspace (ros2_my_robot_ws)

Welcome to ros2_my_robot_ws! This workspace includes a mobile robot with a two-joint arm and camera, ready for simulation, visualization, and control in ROS 2 using Gazebo and RViz.

🚀 Features

Mobile Base: Differential drive with caster wheel support.

Robotic Arm: Two-joint arm (forearm + hand) for manipulation.

Camera: Forward-facing camera with Gazebo sensor simulation.

Interactive Visualization: Use RViz to view robot model, joints, and sensors.

Simulation Ready: Pre-configured for ROS 2 + ros_gz_sim / Gazebo.

🛠 Installation

Clone the repository

cd ~/ros2_ws/src
git clone https://github.com/harishjungshahi/ros2_my_robot_ws.git
cd ~/ros2_ws


Build the workspace

colcon build


Source the workspace

source install/setup.bash

🎮 Launch Simulation

Start your robot in Gazebo and RViz:

ros2 launch my_robot_bringup my_robot_launch.launch.py


This will:

Launch robot_state_publisher to publish joint states from the URDF/XACRO.

Launch joint_state_publisher_gui for interactive joint control.

Start Gazebo with the test world.

Open RViz with the robot model and joint visualization.

📡 Controlling the Robot
Move Arm Joints

Example: move joint0 to position 0.8:

ros2 topic pub -1 /joint0/cmd_pos std_msgs/msg/Float64 "{data: 0.8}"

List Available Topics
ros2 topic list

Inspect Node Info
ros2 node info /robot_state_publisher

🖥 Visualizing in RViz

Open RViz via the launch file.

Add RobotModel and select the robot_description parameter.

Use JointStatePublisher GUI to interactively move joints.

Watch real-time updates in Gazebo or RViz.

🔧 Customization

URDF/XACRO: Modify links, joints, sensors in my_robot_description/urdf.

Gazebo Plugins: Change wheel separation, friction, or camera properties in XACRO gazebo tags.

Launch Files: Adjust world files or RViz configs in my_robot_bringup/launch.

🤝 Contributing

Fork the repository.

Create a branch: git checkout -b feature-name.

Make your changes.

Commit: git commit -am "Add feature".

Push: git push origin feature-name.

Open a Pull Request.

📄 License

This project is licensed under the MIT License – see LICENSE
 for details.
