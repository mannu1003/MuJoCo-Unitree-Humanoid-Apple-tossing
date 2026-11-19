MuJoCo Unitree G1 Humanoid – Apple Tossing Simulation

1. Project Overview

This project implements a physics-based simulation of a Unitree G1 humanoid robot using MuJoCo.

The robot performs a coordinated apple-tossing sequence, transferring an apple between its left and right hands. The simulation demonstrates coordinated humanoid arm movements, inverse kinematics, and projectile motion.

The complete simulation is implemented in a Google Colab notebook.

2. Simulation Features

- Unitree G1 humanoid robot model.
- Alternating apple tosses between the left and right hands.
- Coordinated shoulder, elbow, and wrist movements.
- Inverse Kinematics (IK) for controlling the robot's hands.
- Damped least-squares Jacobian-based IK.
- Cubic spline interpolation for smooth arm trajectories.
- Scripted projectile trajectory of the apple under gravity.
- Coordinated wrist and waist movement.
- Automated simulation rendering and MP4 video generation.

3. Technologies and Libraries Used

- Python
- MuJoCo – Physics-based robot simulation and rendering.
- NumPy – Numerical computations and array operations.
- SciPy – Cubic spline interpolation.
- Mediapy – Video generation and rendering.
- Google Colab – Notebook execution environment.
- MuJoCo Menagerie – Unitree G1 robot model.

4. Software Requirements

- Google Colab or a compatible Python environment.
- Python 3.
- Internet connection for installing dependencies and downloading the robot model.
- Required Python packages:
  - "mujoco"
  - "mediapy"
  - "scipy"
  - "numpy"

5. Installation and Setup

The notebook automatically installs the required packages and downloads the Unitree G1 model from the MuJoCo Menagerie repository.

The installation commands used are:

!pip install -U mujoco mediapy scipy
!git clone -q --depth 1 --filter=blob:none --sparse https://github.com/google-deepmind/mujoco_menagerie.git
!cd mujoco_menagerie && git sparse-checkout set unitree_g1

NumPy is used as a numerical dependency.

6. How to Run the Simulation

1. Open Google Colab: https://colab.research.google.com/
2. Download or open the provided ".ipynb" notebook.
3. Upload the notebook to Google Colab.
4. Connect to a runtime.
5. Execute the notebook cell containing the installation, model setup, simulation, and rendering code.
6. Wait for the robot simulation to complete.
7. The generated simulation video will be displayed in the notebook.

No manual installation of the Unitree G1 model is required because the notebook downloads it automatically.

7. Simulation Parameters

The simulation uses the following main parameters:

Parameter| Value
Robot model| Unitree G1
Number of tosses| 10
Apple flight time| 0.60 seconds
Hold duration| 0.30 seconds
Frame rate| 60 FPS
Video resolution| 1280 × 720
Apple radius| 0.038 m
Gravity| 9.81 m/s²

8. Methodology

The simulation is implemented through the following stages:

1. Model Initialization: The Unitree G1 robot model is loaded from MuJoCo Menagerie, and an apple model and palm sites are added.

2. Motion Planning: Alternating toss and catch events are defined for the left and right hands.

3. Trajectory Generation: Cubic spline interpolation is used to generate smooth hand movement trajectories.

4. Inverse Kinematics: A damped least-squares Jacobian-based inverse kinematics method calculates joint movements to position and orient the robot's hands.

5. Apple Motion: The apple follows a prescribed projectile trajectory during each transfer, with gravitational acceleration included in the trajectory calculation.

6. Rendering: MuJoCo renders the complete motion, and Mediapy generates the final MP4 video.

9. Output

The simulation generates an MP4 video named:

"g1_apple_toss.mp4"

The video shows the Unitree G1 humanoid performing repeated alternating apple-tossing movements.

10. Repository Contents

- "MuJoCo_Unitree_G1_Apple_Tossing.ipynb" – Complete simulation source code and execution notebook.
- "README.md" – Project overview, dependencies, methodology, and execution instructions.

The Unitree G1 model is downloaded automatically from MuJoCo Menagerie during execution.

11. References

- MuJoCo Documentation: https://mujoco.readthedocs.io/
- MuJoCo Menagerie: https://github.com/google-deepmind/mujoco_menagerie
- SciPy Documentation: https://docs.scipy.org/doc/scipy/

12. Author

Mayank Sumalya | Kanxit Dave | Divyansh Somani 
Developed as part of the ME206 supplementary simulation submission.
