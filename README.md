![header](https://capsule-render.vercel.app/api?type=waving&color=0:0f2027,50:203a43,100:2c5364&height=250&section=header&text=Kang%20MyeongJin&fontSize=58&fontColor=ffffff&animation=fadeIn&fontAlignY=36&desc=Physical%20AI%20%7C%20Robot%20Learning%20%7C%20Multimodal%20Systems%20%7C%20Robotics&descAlignY=56&descAlign=50)

# Kang MyeongJin

**Physical AI · Robot Learning · Multimodal Systems · Robotics**

Mechanical Engineering undergraduate at **Soongsil University** interested in learning-based robotics and Physical AI.

My work spans **multimodal perception and sequential learning, real-world robot systems, optimal control, and hardware-aware deep learning**. I am particularly interested in connecting perception, learning, planning, and control on physical robotic systems.

- President of **ACCA**, Soongsil University robotics/autonomous-systems team
- Undergraduate research experience in **hardware-aware neural architecture search and real-time AI**
- Experience with **real-vehicle robotics, ROS/ROS 2, multimodal learning, perception, and optimal control**

---

## Research Interests

- Physical AI & Embodied Intelligence
- Multimodal Robot Learning
- Vision-Language-Action Models
- Robot Learning & Control
- Sim-to-Real and Real-World Robotics
- Efficient & Hardware-Aware AI

---

## Selected Research & Engineering Projects

### [Hardware-Aware Neural Architecture Search](https://github.com/libok03/HW-NAS-YOLO)

**Neural Architecture Search · Multi-Objective Optimization · TensorRT · YOLO**

<!--
Recommended visual extracted from the KCC 2026 poster:
Pareto Front + Hypervolume convergence / validation comparison
Upload as: assets/hw_nas_results.png
Then uncomment:
<p align="center">
  <img src="assets/hw_nas_results.png" width="760" alt="HW-NAS Pareto front and hypervolume convergence">
</p>
<p align="center"><sub>Accuracy–latency Pareto search and convergence comparison against Random Search.</sub></p>
-->

Hardware-aware NAS pipeline for jointly optimizing perception accuracy and inference latency under limited computational resources.

- Designed a YOLO11n-based architecture search space over block type, depth, and attention modules
- Applied `3 → 15 → 50 epoch` multi-fidelity evaluation with Successive Halving
- Used Random Forest uncertainty to selectively measure TensorRT FP16 latency on hardware
- Integrated NSGA-II-based multi-objective optimization for accuracy–latency Pareto search
- Related work presented at the **Korea Computer Congress (KCC) 2026 Undergraduate Session**

---

### [Multi-Camera Perception & Inventory Estimation](https://github.com/libok03/RF_Detr_Based_Inventory_management)

**RF-DETR · YOLO · Multi-Camera Fusion · Temporal Modeling**

<!--
Recommended visual extracted from the final report (system pipeline figure):
5-camera video → 3-frame temporal mean → RF-DETR → Static Interval → Event Candidate → False Endpoint Suppression → Event Merge → Final Event CSV
Upload as: assets/rfdetr_pipeline.png
Then uncomment:
<p align="center">
  <img src="assets/rfdetr_pipeline.png" width="760" alt="RF-DETR multi-camera inventory estimation pipeline">
</p>
<p align="center"><sub>Multi-camera temporal perception pipeline for robust purchase/return event estimation.</sub></p>
-->

Multi-camera perception pipeline for robust product-state and inventory-event estimation in an unmanned retail environment.

- Processed synchronized video from five camera viewpoints
- Trained RF-DETR-based detectors for 60 product classes
- Converted frame-level detections into temporal static intervals and purchase/return event candidates
- Used temporal filtering, pixel-difference validation, and cross-camera persistence to suppress false events caused by occlusion and detector dropout
- Detection performance: **96.76% mAP50–95 · 98.40% Precision · 98.10% Recall**

---

### [Multimodal Sequential Learning for Robotic Planning](https://github.com/libok03/VLA_Driving)

**PyTorch · Multimodal Fusion · Sequential Modeling · Real-Time Inference**

Learning-based planning system evaluated in the **MORAI autonomous-driving simulation environment** as a testbed for multimodal robot learning.

- Fused front/left/right camera images, LiDAR BEV, robot state, localization, and route information
- Built synchronized temporal datasets from ROS recordings
- Developed learning-based sequential prediction models for motion planning
- Measured approximately **18.4 ms model inference latency** and **20 ms end-to-end processing latency** on the target compute environment

> MORAI is used here as an experimental robotics platform; autonomous driving itself is not my primary research direction.

---

### [ERP42 Real-Robot Planning, State Machine & MPC Optimization](https://github.com/libok03/ACCA_2025)

**ROS 2 · Path Planning · State Machine · Sensor Integration · MPC**

<!--
Upload the first photo from this conversation as: assets/acca_2025_real_vehicle.jpg
Then uncomment:
<p align="center">
  <img src="assets/acca_2025_real_vehicle.jpg" width="720" alt="ERP42 real-vehicle integration and testing">
</p>
<p align="center"><sub>Real-vehicle integration and testing with the ERP42 platform.</sub></p>
-->

Real-world robotics project using the ERP42 platform.

**My role:** Path Planning · State Machine · Sensor Integration · MPC Optimization

- Developed path-generation and path-management pipelines from localization measurements using cubic-spline interpolation
- Implemented mission-dependent state transitions for normal driving, obstacle handling, U-turn, and other scenarios
- Worked with GNSS, IMU, LiDAR, odometry, and localization inputs in the ROS 2 system
- Analyzed lateral error, heading error, velocity error, and oscillation during real-vehicle testing
- Tuned MPC cost matrices and vehicle constraints to improve trajectory-tracking stability and control response

---

### [MORAI-Based Multimodal Robotics System](https://github.com/libok03/ACCA2026)

**MORAI · ROS · Simulation · Multimodal Data · Learning-Based Planning**

Simulation-based robotics system developed for the 2026 AI/SW Mobility Competition.

- Built synchronized data-collection pipelines for camera, LiDAR, localization, vehicle state, and route information
- Designed scenario-based recording and labeling workflows
- Integrated perception, planning, and control components in the MORAI environment
- Used the simulator as an experimental platform for multimodal learning and real-time planning

---

### [LeRobot SO-101 Teleoperation](https://github.com/libok03/maker_fair_2026_teleoperation_lerobot)

**LeRobot · Teleoperation · Robot Learning**

- Built a master–slave teleoperation workflow with the SO-101 platform
- Worked with physical robot control and demonstration-data collection
- Explored teleoperation as a data interface for imitation-learning and robot-learning pipelines

---

## Publication

**Latency-Calibrated Hardware-Aware Neural Architecture Search for Small Object Detection in Autonomous Driving Environments**  
Hyeonbeen Jang · **MyeongJin Kang**  
*Korea Computer Congress (KCC) 2026 · Undergraduate Session*

---

## Research & Leadership

### Undergraduate Research Intern
**Physical AI Specialized Laboratory, Soongsil University · 2026**

- Hardware-aware neural architecture search
- Real-time inference optimization
- Deep-learning experiments for resource-constrained systems

### President
**ACCA, Soongsil University · 2026**

- Coordinated robotics and autonomous-system projects
- Managed integration work across perception, localization, planning, control, and learning components
- Organized real-robot and simulation experiments

<!--
Upload the second photo from this conversation as: assets/acca_team.jpg
Then uncomment:
<p align="center">
  <img src="assets/acca_team.jpg" width="720" alt="ACCA team at Soongsil University">
</p>
<p align="center"><sub>ACCA team, Soongsil University.</sub></p>
-->

---

## Technical Skills

**Programming**  
Python · C++ · MATLAB

**Machine Learning**  
PyTorch · TensorRT · YOLO · RF-DETR · Multimodal Fusion · Sequential Models · Reinforcement Learning

**Robotics**  
ROS · ROS 2 · RViz · Gazebo · MoveIt 2 · LeRobot

**Planning & Control**  
MPC · Stanley Controller · PID · State Machines · Path Planning

**Perception & Sensors**  
Camera · LiDAR · IMU · GNSS · OpenCV · Multi-Camera Fusion

**Systems**  
Linux · Docker · Git · CUDA · TensorBoard

---

## Other Experiments

[PPO Swing-Up](https://github.com/libok03/PPO_SwingUp) · [Atari DQN](https://github.com/libok03/Atari_DQN_Agent) · [CartPole RL](https://github.com/libok03/CartPole_RL)

---

## Contact

- Email: **markpiano01@gmail.com**
- GitHub: **[@libok03](https://github.com/libok03)**
