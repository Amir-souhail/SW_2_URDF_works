
# SWtoURDFExerciseproject

This repository showcases my first attempt at converting a SolidWorks robotic arm assembly into a URDF (Unified Robot Description Format) for use in ROS (Robot Operating System). The CAD parts were provided in the tutorial by [Age of Robotics](https://github.com/ageofrobotics/urdf_tutorial), and I focused on assembling them into a functional URDF model.

---

## 🗂 Repository Structure

```
SWtoURDFproject/
├── CAD_Files/          # Original SolidWorks parts and assembly files
├── urdf/               # Generated URDF files
├── meshes/             # STL files for visual representation
├── launch/             # ROS launch files to visualize in RViz
└── README.md
```

---

## ⚙️ Requirements

* **Software**:

  * SolidWorks (for CAD model viewing or modification)
  * ROS (Robot Operating System)
  * SolidWorks to URDF Exporter (e.g., [sw\_urdf\_exporter](https://github.com/ros-industrial/solidworks_urdf))
* **Hardware**:

  * Optional: Robotic arm hardware for testing

---

## 🚀 Setup Instructions

1. **Clone the repository**:

   ```bash
   git clone https://github.com/yourusername/SWtoURDFproject.git
   cd SWtoURDFproject
   ```

2. **Open CAD files**:

   * Open `.SLDPRT` and `.STEP` files in SolidWorks to inspect or modify the robotic parts.

3. **Generate URDF**:

   * Use the SolidWorks to URDF Exporter to convert the assembly into a URDF model.

4. **Integrate with ROS**:

   * Place URDF and STL files in a ROS workspace.
   * Launch the visualization using the provided launch files:

     ```bash
     roslaunch sw_to_urdf_project display.launch
     ```

---

## 📚 References

* GitHub Repository: [ageofrobotics/urdf\_tutorial](https://github.com/ageofrobotics/urdf_tutorial)
* YouTube Channel: [Age of Robotics](https://www.youtube.com/@Age.of.Robotics)
* Tutorial Playlist: [SolidWorks to URDF Series](https://www.youtube.com/playlist?list=PLeEzO_sX5H6TBD6EMGgV-qdhzxPY19m12)

---

## 🛠️ Contributions

Contributions, improvements, or suggestions are welcome! Please fork the repository and submit a pull request.

---

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

