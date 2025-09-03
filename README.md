# ROS2 My Robot Workspace (`ros2_my_robot_ws`) 🚗🤖

Welcome to **ros2_my_robot_ws**! This workspace includes a **mobile robot** with a **two-joint arm** and **camera**, ready for simulation, visualization, and control in **ROS 2** using **Gazebo** and **RViz**.

---

## 🚀 Features

| Component        | Description |
|-----------------|-------------|
| **Mobile Base**  | Differential drive with caster wheel support. |
| **Robotic Arm**  | Two-joint arm (forearm + hand) for manipulation. |
| **Camera**       | Forward-facing camera simulated in Gazebo. |
| **Visualization**| Use RViz to view robot model, joints, and sensors in real-time. |
| **Simulation**   | Pre-configured for ROS 2 + ros_gz_sim / Gazebo. |

---

## 🛠 Installation

### 1️⃣ Clone Repository

```bash
cd ~/ros2_ws/src
git clone https://github.com/harishjungshahi/ros2_my_robot_ws.git
cd ~/ros2_ws
2️⃣ Build Workspace
bash
Copy code
colcon build
3️⃣ Source Workspace
bash
Copy code
source install/setup.bash
🎮 Launch Simulation
Run the robot in Gazebo and RViz:

bash
Copy code
ros2 launch my_robot_bringup my_robot_launch.launch.py
✅ This will:

Start robot_state_publisher for URDF/XACRO joints

Start joint_state_publisher_gui for interactive joint control

Launch Gazebo with the test world

Open RViz with the robot model

<details> <summary>💡 Tip: Interactive Control</summary>
In RViz, add RobotModel → select robot_description.

Use JointStatePublisher GUI to move joints interactively.

Watch changes live in Gazebo or RViz.

</details>
📡 Controlling the Robot
Move Arm Joints
bash
Copy code
ros2 topic pub -1 /joint0/cmd_pos std_msgs/msg/Float64 "{data: 0.8}"
List Available Topics
bash
Copy code
ros2 topic list
Inspect Node Info
bash
Copy code
ros2 node info /robot_state_publisher
<details> <summary>💡 Tip: Make it interactive</summary>
Open multiple terminals: one for publishing commands, one for monitoring topics, and one for RViz.

Move joints using sliders and watch real-time robot motion.

</details>
🔧 Customization
URDF/XACRO: Modify links, joints, sensors in my_robot_description/urdf.

Gazebo Plugins: Adjust wheel separation, friction, or camera properties in the XACRO gazebo tags.

Launch Files: Change world files or RViz configs in my_robot_bringup/launch.

🤝 Contributing
Fork the repository

Create a branch:

bash
Copy code
git checkout -b feature-name
Make your changes

Commit:

bash
Copy code
git commit -am "Add feature"
Push:

bash
Copy code
git push origin feature-name
Open a Pull Request

📄 License
MIT License – see LICENSE for details.
