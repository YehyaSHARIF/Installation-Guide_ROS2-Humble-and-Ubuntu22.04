# Install ROS 2 Humble Hawksbill on Ubuntu 22.04

Follow these steps to install the full version of ROS 2 Humble:

---

## 1. Set Locale

Ensure your system locale is set to `en_US.UTF-8`:

```bash
sudo apt update
sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8
```

---

## 2. Enable Ubuntu Universe Repository

Enable the Universe repository:

```bash
sudo apt install software-properties-common
sudo add-apt-repository universe
```

---

## 3. Add ROS 2 Repository

Import the ROS 2 GPG key and add the ROS 2 repository:

```bash
sudo apt update
sudo apt install curl -y
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg

echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] \
http://packages.ros.org/ros2/ubuntu $(lsb_release -cs) main" | \
sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
```

---

## 4. Install ROS 2 Packages

Update the package index and install ROS 2 Desktop:

```bash
sudo apt update
sudo apt upgrade
sudo apt install ros-humble-desktop
```

> This installs the Desktop version (ROS, RViz, demos, tutorials).

---

## 5. Environment Setup

Source ROS 2 setup script automatically when opening a terminal:

```bash
echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

---

## 6. Install Dependencies for Building Packages

Install development tools:

```bash
sudo apt install -y \
  python3-colcon-common-extensions \
  python3-rosdep \
  python3-vcstool \
  python3-argcomplete
```

Initialize `rosdep`:

```bash
sudo rosdep init
rosdep update
```

---

## 7. Verify Installation

Test ROS 2 with a simple demo:

- In Terminal 1 (talker):
  ```bash
  ros2 run demo_nodes_cpp talker
  ```

- In Terminal 2 (listener):
  ```bash
  ros2 run demo_nodes_cpp listener
  ```

You should see messages being published and received, confirming ROS 2 is working.

- In a Terminal:
   ```bash
  source /opt/ros/humble/setup.bash
  ros2 run turtlesim turtlesim_node
  ```
---

> **More Info**: See the [ROS 2 Humble documentation](https://docs.ros.org/en/humble/Installation.html) for advanced topics.

---
