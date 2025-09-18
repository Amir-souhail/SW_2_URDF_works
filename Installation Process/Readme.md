# SolidWorks to URDF Exporter Setup

This repository documents my workflow for setting up and using the **SolidWorks URDF Exporter** to convert assemblies into **URDF (Unified Robot Description Format)** files.  
The exported URDF files can then be used in robotics applications such as **ROS**, **Gazebo**, and **RViz**.

The exporter was originally authored and maintained by **Stephen Brawner**, with past support from PickNik Consulting, Verb Surgical, Open Robotics, and Willow Garage.  
Official repository: [ros/solidworks_urdf_exporter](https://github.com/ros/solidworks_urdf_exporter)

---

## SolidWorks Version Requirements
- Minimum supported version: **SolidWorks 2018 SP5**  
- Verified releases from the official repo:
  - [SolidWorks 2021 – Exporter v1.6.1](https://github.com/ros/solidworks_urdf_exporter/releases/tag/1.6.1)  
  - [SolidWorks 2020 – Exporter v1.6.0](https://github.com/ros/solidworks_urdf_exporter/releases/tag/1.6.0)  
  - [SolidWorks 2019 on 2018 SP5 – Exporter v1.5.1](https://github.com/ros/solidworks_urdf_exporter/releases/tag/1.5.1)  

✅ **Tested and working on SolidWorks 2025 SP0.0** (with admin installation + API SDK setup).  

---

## Installation Steps (My Process)

### 1. Install Visual Studio
- Download and install **Visual Studio 2017 or later**.  
- During setup, enable **.NET desktop development**:  
  - `Visual Studio → Tools → Get Tools and Features...`  
  - Check **.NET desktop development**  
  - Select **Modify**

### 2. Install SolidWorks API Tools / SDK
- The exporter requires the **SolidWorks API SDK**.  
- The official help docs were unclear for my version, so I used this YouTube guide:  
  [▶ SolidWorks API SDK Installation Tutorial](https://youtu.be/9QB2gtHUeT0)

### 3. Run Installers with Administrator Privileges
- **Important:** All `.exe` files (Visual Studio, SDK, exporter setup) must be run as **Administrator**.  
- Without admin rights, some components fail to install or register correctly.

### 4. Build and Install the Exporter
- Open the project: `sw2urdf/SW2URDF.sln` in Visual Studio.  
- Launch Visual Studio as **Administrator**.  
- Debug setup:  
  - Right-click **SW2URDF** in Solution Explorer → Properties → Debug tab  
  - Set **Configuration** to `Debug`  
  - Set **Start external program** to your SolidWorks executable  
    (e.g., `C:\Program Files\SOLIDWORKS Corp\SOLIDWORKS\SLDWORKS.exe`)  
- Build and install.  

---

## Usage
1. Open your SolidWorks assembly.  
2. Go to the **Tools menu** → select **Export to URDF**.  
   > ⚠️ Note: The exporter does **not** appear under *Save As* or the *File* menu.  
3. Use the wizard to generate a URDF package (with meshes).  
4. Import the generated URDF into **ROS**, **Gazebo**, or **RViz**.  

---

## Mesh Conversion (Optional)
If you want colored meshes in RViz, you can convert 3DXML → DAE:  

```bash
pip3 install scikit-robot -U
convert-urdf-mesh <URDF_PATH> --output <OUTPUT_URDF_PATH>

Troubleshooting

AxImp.exe error → Check if .NET tools are installed. If still broken, install the Windows 10 SDK.

Resource.resx error → If sw2urdf/SW2URDF/Resources.resx exists but is empty, delete it. Then in Visual Studio:

Right-click SW2URDF → Properties → Resources tab → create a new file.

References

GitHub: ros/solidworks_urdf_exporter

YouTube: SolidWorks API SDK Installation Tutorial
