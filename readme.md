source /home/amax/data/wjh/NavRL_workspace/src/ros1/uav_simulator/gazeboSetup.bash
# Launch the gazebo simulator
roslaunch uav_simulator start.launch

# Start the perception and safety module
roslaunch navigation_runner safety_and_perception_sim.launch

# Run the navigation node
conda activate NavRL
rosrun navigation_runner navigation_node.py




export VK_ICD_FILENAMES=/usr/share/vulkan/icd.d/nvidia_icd.json
export LIBGL_ALWAYS_INDIRECT=0
export MESA_LOADER_DRIVER_OVERRIDE=nvidia
export __GLX_VENDOR_LIBRARY_NAME=nvidia


# 如果RVIZ打不开
export RVIZ_RENDER_OPTS="-opengl 2.1"
roslaunch navigation_runner safety_and_perception_sim.launch

# 配置：英伟达535驱动