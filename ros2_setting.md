# ROS2

## ROS2 install


[ROS2 Foxy](https://docs.ros.org/en/foxy/Installation/Ubuntu-Install-Debians.html#id4vscode)


## make useful bashrc lines

```bash
# Create switch_to_noetic.sh
cat <<EOF > ~/switch_to_noetic.sh
#!/bin/bash
# Unset ROS 2 Foxy environment variables
unset ROS_DISTRO
unset ROS_PACKAGE_PATH
unset AMENT_PREFIX_PATH
unset CMAKE_PREFIX_PATH
unset PYTHONPATH

# Source ROS 1 Noetic environment
source /opt/ros/noetic/setup.bash
echo "Switched to ROS 1 Noetic environment"
EOF

# Create switch_to_foxy.sh
cat <<EOF > ~/switch_to_foxy.sh
#!/bin/bash
# Unset ROS 1 Noetic environment variables
unset ROS_DISTRO
unset ROS_PACKAGE_PATH
unset AMENT_PREFIX_PATH
unset CMAKE_PREFIX_PATH
unset PYTHONPATH

# Source ROS 2 Foxy environment
source /opt/ros/foxy/setup.bash
echo "Switched to ROS 2 Foxy environment"
EOF

# Grant execute permissions
chmod +x ~/switch_to_noetic.sh
chmod +x ~/switch_to_foxy.sh

# Add aliases to .bashrc
echo "alias noetic='source ~/switch_to_noetic.sh'" >> ~/.bashrc
echo "alias foxy='source ~/switch_to_foxy.sh'" >> ~/.bashrc

# Apply .bashrc changes
source ~/.bashrc

```

