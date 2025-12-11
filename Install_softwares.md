# ROS 2 Environment Setup — Gazebo, RViz2, Terminator, PlotJuggler

This README provides step-by-step instructions to install a complete ROS 2 environment on **Ubuntu 22.04**, including:

- Gazebo (Ignition Fortress or Garden)  
- RViz2  
- Terminator  
- PlotJuggler  
- Basic system and ROS 2 prerequisites  

---

## 1️⃣ System Prerequisites

Update your Ubuntu system:

```bash
sudo apt update && sudo apt upgrade -y

Install essential tools and dependencies:

sudo apt install -y \
    build-essential \
    curl \
    wget \
    git \
    lsb-release \
    gnupg \
    python3-colcon-common-extensions \
    python3-rosdep \
    python3-argcomplete

Initialize rosdep:

sudo rosdep init
rosdep update


## 2 Install Gazebo (Fortress or Garden)


sudo apt install gazebo

Launch Gazebo:

gazebo

## 4️⃣ Install RViz2

RViz2 is included in ros-humble-desktop.

If needed, install manually:

sudo apt install ros-humble-rviz2 -y

Run RViz2:

rviz2

## 5️⃣ Install Terminator

Terminator allows efficient multi-terminal workflows for ROS 2.

sudo apt install terminator -y

Run Terminator:

terminator

## 6️⃣ Install PlotJuggler

PlotJuggler is used to visualize ROS 2 topics (real-time or bag files).

Install with ROS 2 plugins:

sudo apt install ros-humble-plotjuggler ros-humble-plotjuggler-ros -y

Run PlotJuggler:

ros2 run plotjuggler plotjuggler

## 7️⃣ Useful ROS 2 Tools
colcon (build system)

Already installed above.

Build a ROS 2 workspace:

colcon build --symlink-install

rqt (graphical tools)

sudo apt install ros-humble-rqt ros-humble-rqt-common-plugins -y

## 8️⃣ Verification
Test ROS 2 communication

Open two terminals (using Terminator if preferred).

Terminal 1:

ros2 run demo_nodes_cpp talker

Terminal 2:

ros2 run demo_nodes_cpp listener

You should see messages being published and received.
Test Gazebo + ROS 2 integration

ros2 launch ros_gz_sim gz_sim.launch.py

✔️ Installation Complete!

You now have a full robotics development environment including:

    ROS 2 Humble

    Gazebo Fortress / Garden

    RViz2

    Terminator

    PlotJuggler

    Linux development tools

    ROS 2 build and debugging utilities

Your system is now ready for simulation, visualization, development, and real robotics testing 🚀
🧩 Optional Enhancements
🔹 Install Navigation2 (Nav2)

sudo apt install ros-humble-navigation2 ros-humble-nav2-bringup -y

🔹 Install SLAM Toolbox

sudo apt install ros-humble-slam-toolbox -y

🔹 Install ROS Bags Tools

sudo apt install ros-humble-ros2bag ros-humble-rosbag2* -y


---

If you'd like, I can also prepare:

✅ A French version  
✅ A printable PDF version  
✅ A version including Docker setup  
✅ A version adapted for ROS 2 Iron / Jazzy



