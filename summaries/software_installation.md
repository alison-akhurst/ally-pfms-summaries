## Customising Linux Install for PfMS
You will need to download sever packages for the subject and install ROS (execute the commands below in terminal window)

For students in Australia I would suggest to replace the mirror (the location where ubuntu packages are stored) with an Australian server. This will speed up your instantiation significantly (possibly ten fold), as the installation can be ~15-30 minutes.

All of the below commands need to be executed in the terminal. Copy / paste each instruction (command) : you need to copy/paste each line one after the other. 

```bash
sudo sed -i 's/http:\/\/archive.ubuntu.com\/ubuntu\//http:\/\/mirror.internode.on.net\/pub\/ubuntu\/ubuntu\//' /etc/apt/sources.list
```


You will need to add the ROS 2 apt repository to your system. First ensure that the Ubuntu Universe repository is enabled.
```bash
sudo apt install software-properties-common
sudo add-apt-repository universe
```

Now add the ROS 2 GPG key with apt.

```bash
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
```

Then add the repository to your sources list.

```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
```

Update your apt repository caches after setting up the repositories.  ROS 2 packages are built on frequently updated Ubuntu systems. It is always recommended that you ensure your system is up to date before installing new packages.

```bash 
sudo apt update
sudo apt upgrade
```

Now install ROS2 (~700MB of data and 2.5GB of disk space needed)

```bash
sudo apt install ros-humble-desktop
```

Install gazebo, a physics simulator integrated in ROS which needs ~ 140MB download and will occupy 651MB of your disk space.

```bash
sudo apt install ros-humble-xacro ros-humble-gazebo-ros ros-humble-gazebo-plugins ros-humble-controller-manager ros-humble-rqt-robot-steering ros-humble-robot-localization ros-humble-gazebo-ros2-control ros-humble-joint-trajectory-controller ros-humble-joint-state-broadcaster ros-humble-diff-drive-controller ros-humble-imu-tools ros-humble-gazebo-ros-pkgs ros-humble-joint-state-publisher-gui ros-humble-joint-state-publisher

sudo apt install python3-colcon-common-extensions

sudo apt install ros-dev-tools
```

Finally, setup your system path.

```bash
echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc 
echo "export GAZEBO_RESOURCE_PATH=/usr/share/gazebo-11/" >> ~/.bashrc
```


Create a workspace for ROS2

```bash
source ~/.bashrc

mkdir -p ~/ros2_ws/src

cd ~/ros2_ws

colcon build --symlink-install

echo "source ${HOME}/ros2_ws/install/setup.bash" >> ~/.bashrc
```

Lastly, free up space on your computer 

```bash
sudo apt-get clean
```


## Installation and Set Up for pfms-support, Ros2 and, Gazebo

If not done already:

```bash
cd ~/git
git clone git@github.com:41012/pfms-support.git
```

Proceed to install the pipes library, which has been supplied to allow using the physics simulator, at present bypassing the ROS framework for students.

```bash
cd pfms-support
sudo apt install ./packages/pipes_3.0.2-humble_amd64.deb
sudo ldconfig
```
If you get following warning you can ignore it `N: Download is performed unsandboxed as root as file`, it's just stating the package is installed from a local file.

If not done already, link the `pfms_ros` folder to your `ros2_ws/src`

```bash
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws/src
ln -s ~/git/pfms-support/pfms-ros 
```

Now we can make the package.

```bash
cd ~/ros2_ws
colcon build --symlink-install
source ~/.bashrc
```

**You should now have all the required software**.  and can go back to [README](README.md)

If you have an error such as

```bash
CMake Error at CMakeLists.txt:15 (find_package):
  By not providing "Findament_cmake.cmake" in CMAKE_MODULE_PATH this project
  has asked CMake to find a package configuration file provided by
  "ament_cmake", but CMake did not find one.
```

Then try again installing the tools

```bash
sudo apt install ros-dev-tools
```

Also check that your `.bashrc` file sources the ros `setup.bash` file. You can do so by
`tail ~/.bashrc`

Where you should see `source /opt/ros/humble/setup.bash`  and something like `source /home/XXXXXX/ros2_ws/install/setup.bash` displayed on screen (wheer `XXXX` is your username and thus it depends on your device username. The `\opt\ros` are packages supplied by ros and part of system while those in  `ros2_ws` are those installed for our subject.

If `/opt/ros` it is missing then execute.

```bash
echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc
```
If the `ros_ws`  is missing

```bash
echo "source ${HOME}/ros2_ws/install/setup.bash" >> ~/.bashrc
```
Then execute below to update the system, this makes your system aware of software installed in the two locations (all packages and support files).
```bash
source ~/.bashrc
```


