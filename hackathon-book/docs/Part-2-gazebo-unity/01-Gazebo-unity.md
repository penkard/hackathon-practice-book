


### **3.2 Gazebo: The High-Fidelity Physics Engine**

**Gazebo** is the dedicated physics-based simulation environment that integrates natively with ROS 2. Its primary role is to handle the complex computations of **Rigid Body Dynamics**.

#### **Gazebo Technical Components**

1.  **Physics Engine Integration:** Gazebo is built on pluggable physics libraries (like ODE, Bullet, or DART). It calculates:
    * **Gravity and Inertia:** Accurate modeling of mass distribution.
    * **Friction and Contact:** Realistic interactions between the robot's links and the world surfaces.
    * **Joint Dynamics:** Simulating motor limits, velocity, and torque control for the robot's joints.
2.  **Sensor Simulation:** Crucial for training perception algorithms. Gazebo uses internal ray-tracing and rendering to generate synthetic sensor data:
    * **LiDAR/Laser Scans:** Simulates range data based on the virtual environment's geometry.
    * **Depth Cameras:** Generates depth maps (3D point clouds).
    * **Noise Models:** Users can inject Gaussian, Perlin, or other noise to mimic real-world sensor imperfections, closing the "sim-to-real gap."
3.  **World Definition (SDF):** The environment is defined using the **Simulation Description Format (SDF)**. SDF is an XML-based file that describes the objects, terrain, lights, and physics properties of the virtual "World."

---