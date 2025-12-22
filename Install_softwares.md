2️⃣ Essential Development Tools
sudo apt install -y \
  build-essential \
  curl \
  wget \
  git \
  lsb-release \
  gnupg

3️⃣ Configure ROS 2 Repository (Recommended Method)

⚠️ Do not use apt-key (deprecated).
This setup uses the official ROS keyring method.

Add ROS keyring
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key \
  -o /usr/share/keyrings/ros-archive-keyring.gpg

Add ROS 2 repository
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] \
http://packages.ros.org/ros2/ubuntu jammy main" | \
sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null


Update package index:

sudo apt update

4️⃣ Install ROS 2 Humble

Recommended full desktop installation:

sudo apt install -y ros-humble-desktop


Source ROS:

source /opt/ros/humble/setup.bash


(Optional) Automatically source ROS on startup:

echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc

5️⃣ Fix Python / catkin Dependency Conflicts (IMPORTANT)

This step prevents known conflicts between Ubuntu Python packages and ROS 2 dependencies.

Remove conflicting Ubuntu package:

sudo apt remove -y python3-catkin-pkg
sudo dpkg --configure -a
sudo apt --fix-broken install


Install ROS-compatible versions:

sudo apt install -y python3-catkin-pkg-modules python3-catkin-pkg


Verify package origins:

apt-cache policy python3-catkin-pkg python3-catkin-pkg-modules


Both packages must come from packages.ros.org.

6️⃣ Install Gazebo
Option A — Gazebo Classic
sudo apt install -y gazebo


Run:

gazebo

Option B — Gazebo with ROS 2 integration (Recommended)
sudo apt install -y ros-humble-ros-gz-sim


Launch:

ros2 launch ros_gz_sim gz_sim.launch.py

7️⃣ Install RViz2

RViz2 is included in ros-humble-desktop, but can be installed explicitly:

sudo apt install -y ros-humble-rviz2


Run:

rviz2

8️⃣ Install Terminator (Multi-Terminal)
sudo apt install -y terminator


Run:

terminator

9️⃣ Install PlotJuggler

PlotJuggler is used to visualize ROS 2 topics in real time or from bag files.

sudo apt install -y \
  ros-humble-plotjuggler \
  ros-humble-plotjuggler-ros


Run:

ros2 run plotjuggler plotjuggler

🔧 ROS 2 Development Tools
colcon (Build System)
sudo apt install -y python3-colcon-common-extensions


Build a workspace:

colcon build --symlink-install

rqt (Graphical Tools)
sudo apt install -y ros-humble-rqt ros-humble-rqt-common-plugins

✅ Verification

Test ROS 2 communication.

Open two terminals.

Terminal 1:

ros2 run demo_nodes_cpp talker


Terminal 2:

ros2 run demo_nodes_cpp listener


✔️ Messages should be published and received correctly.

🚀 Environment Ready

Your system now includes:

ROS 2 Humble

Gazebo / ROS-GZ

RViz2

Terminator

PlotJuggler

colcon & rqt

Clean dependency state

You are ready for simulation, visualization, development, and real robot experiments.

🧩 Optional Packages
Navigation2
sudo apt install -y ros-humble-navigation2 ros-humble-nav2-bringup

SLAM Toolbox
sudo apt install -y ros-humble-slam-toolbox

ROS bag tools
sudo apt install -y ros-humble-rosbag2*

📄 Notes

ROS 2 Humble is officially supported on Ubuntu 22.04

Avoid mixing Ubuntu ROS packages with ROS repository packages

Always use packages.ros.org for ROS 2 dependencies

🤝 Contributions

Contributions, fixes, and improvements are welcome.
Feel free to open issues or submit pull requests.
