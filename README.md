# catkin_ws3
Move catkin_ws and ROS_catkin_ws to your home directory  
If you have installed ROS before then run followings:
### ensure there are no ros packages
```
sudo apt-get remove --autoremove ros-*
```
#### check for updates
```
sudo apt update
```
#### ensure /etc/ros removal
```
sudo rm -rf /etc/ros/
```

# install the python3 libraries
```
sudo apt install -y python3 python3-dev python3-pip build-essential
```
# Remove python2
```
sudo apt purge -y python2.7-minimal
```
# link python -> python3
```
sudo ln -s /usr/bin/python3 /usr/bin/python
```
# Same for pip
```
sudo ln -s /usr/bin/pip3 /usr/bin/pip
```
# install the ros dependencies
```
sudo -H pip3 install --no-cache-dir --ignore-installed rosdep rospkg rosinstall_generator rosinstall wstool vcstools catkin_tools catkin_pkg
```
# initialize catkin build environment
```
sudo rosdep init && rosdep update
```
# setup environment and isntall dependencies
```
cd ~/ROS_catkin_ws
export ROS_PYTHON_VERSION=3
```
# install wxPython
Install wxpython from this site https://extras.wxpython.org/wxPython4/extras/linux/gtk3/
If you are Ubuntu-18.04 then you can run this below;
```
pip3 install -U -f https://extras.wxpython.org/wxPython4/extras/linux/gtk3/ubuntu-18.04 wxPython
```
# build ros
```
sudo chmod +x catkin_make_isolated
./catkin_make_isolated
```

# export python path
```
export PYTHONPATH=/usr/lib/python3/dist-packages
```
# source setup
```
source ~/ros_catkin_ws/install_isolated/setup.bash
```

#install missing python3 packages
```
pip3 install pyOpenSSL twisted autobahn bson hyperopt hyperas
pip3 uninstall bson
pip3 install pymongo
sudo -H pip3 install service_identity
```
#Build catkin_ws
```
cd ~/catkin_ws
chmod +x catkin_make
./catkin_make
source ~/catkin_ws/devel/setup.bash
```
I recommend to add
```
source ~/ros_catkin_ws/install_isolated/setup.bash
```
and
```
source ~/catkin_ws/devel/setup.bash
```
to your ~/.bashrc