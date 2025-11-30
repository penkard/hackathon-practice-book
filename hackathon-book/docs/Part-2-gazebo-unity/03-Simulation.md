### **3.4 The End-to-End Simulation Workflow**

The overall process connects the static robot definition with the dynamic environment and the operational control code.

1.  **Modeling:** The robot's kinematic, visual, and inertial properties are defined in the **URDF** (Unified Robot Description Format) file.
2.  **World Setup:** An **SDF** file is created for the environment, often containing the URDF model along with the surrounding static objects.
3.  **Launch & Control:**
    * A ROS 2 **Launch File** starts Gazebo (or the Unity environment) and spawns the robot model.
    * Crucially, the ROS 2 **Controller Nodes** (written in Python/`rclpy` or C++/`rclcpp`) are also launched.
    * The simulated sensors publish data to ROS 2 **Topics** (e.g., `/camera/image_raw`).
    * The controller nodes subscribe to this data, calculate motor commands, and publish back to the simulated actuator topics (e.g., `/joint_controllers/commands`).
4.  **Data Analysis:** Simulated data can be recorded using **rosbag** for later analysis and debugging, just like real robot data.