![header](https://capsule-render.vercel.app/api?type=waving&color=0:0f2027,50:203a43,100:2c5364&height=250&section=header&text=Kang%20MyeongJin&fontSize=58&fontColor=ffffff&animation=fadeIn&fontAlignY=36&desc=Physical%20AI%20%7C%20Robot%20Learning%20%7C%20Multimodal%20Systems%20%7C%20Robotics&descAlignY=56&descAlign=50)

# Kang MyeongJin · 강명진

**Mechanical Engineering undergraduate at Soongsil University**  
**Physical AI · Robot Learning · Multimodal Systems · Robotics**

I work on connecting **perception, learning, planning, and control** in robotic systems. My experience spans real-vehicle autonomy on ERP42, multi-camera product perception, hardware-aware model optimization, learning-based driving in MORAI, and physical robot-arm integration.

On ERP42, I worked on path planning, state machines, sensor integration, and MPC tuning. In learning-based driving, my work extends from collecting and preparing data to model development, training, evaluation, and ROS runtime integration. My current SO-101 work brings motion planning and measured joint feedback together on a physical manipulator.

Alongside technical work, I serve as **President of ACCA**, Soongsil University's robotics/autonomous-systems team, coordinating projects and system integration across perception, localization, planning, control, and learning.

[Email](mailto:markpiano01@gmail.com) · [GitHub](https://github.com/libok03)

## Portfolio overview

| Project | Focus | My work / project scope |
| :--- | :--- | :--- |
| [ERP42 autonomy](https://github.com/libok03/ACCA_2025) | Real-vehicle planning & control | Path planning, state-machine design, sensor integration, MPC tuning |
| [Multi-camera inventory](https://github.com/libok03/RF_Detr_Based_Inventory_management) | Perception & temporal estimation | Temporal event-estimation pipeline and report preparation |
| [Hardware-aware NAS](https://github.com/libok03/HW-NAS-YOLO) | Accuracy–latency optimization | Model training, experimental evaluation, manuscript and poster preparation |
| [Learning-based driving](https://github.com/libok03/VLA_Driving) | Policy learning & runtime integration | Model development, data preparation, training, inference, and ROS integration |
| [SO-101 manipulation](https://github.com/libok03/maker_fair_2026_teleoperation_lerobot) | Simulation & physical robot execution | Ongoing project covering calibration, MoveIt 2 integration, and hardware feedback |

---

## Selected Research & Engineering Projects

### ERP42 real-vehicle robotics
[**ACCA 2025 →**](https://github.com/libok03/ACCA_2025)  
`ROS 2` `Path Planning` `State Machines` `MPC` `Sensor Integration`

<p align="center">
  <img src="assets/acca_2025_real_vehicle.jpg" width="560" alt="ERP42 real-vehicle integration and testing">
</p>

**My contribution:** path planning, state-machine design, sensor integration, and MPC optimization/tuning on the ERP42 platform.


---

### Multi-camera inventory estimation
[**RF-DETR Based Inventory Management →**](https://github.com/libok03/RF_Detr_Based_Inventory_management)  
`RF-DETR` `YOLO` `OpenCV` `Temporal Filtering`

<p align="center">
  <img src="assets/rfdetr_pipeline.png" width="720" alt="Multi-camera product detection and inventory estimation pipeline">
</p>

**5 camera views · 60 product classes**  
Converting frame-level detections into class counts, temporally filtered observations, and fused inventory estimates.

**My contribution:** temporal event-estimation pipeline development and final report writing/organization. The public implementation includes detection, count extraction, temporal filtering, and class-wise camera fusion.


---

### Hardware-aware neural architecture search
[**HW-NAS-YOLO →**](https://github.com/libok03/HW-NAS-YOLO)  
`YOLO11n` `NSGA-II` `Ray` `TensorRT FP16`

<p align="center">
  <img src="assets/hw_nas_results.png" width="560" alt="HW-NAS accuracy-latency Pareto front and hypervolume convergence comparison">
  <br><sub>Accuracy–latency Pareto search and convergence comparison</sub>
</p>

Searching detector architectures under a joint **accuracy–latency objective**.

- **3 → 15 → 50 epochs:** multi-fidelity evaluation with Successive Halving.
- Block type, depth, and attention-module search with pretrained weight inheritance.
- Random Forest latency prediction with selective TensorRT FP16 hardware measurements.

**My contribution:** model training, experimental evaluation, manuscript writing, and poster preparation.


---

### Learning-based autonomous driving
[**VLA_Driving →**](https://github.com/libok03/VLA_Driving)  
`PyTorch` `TCP` `Imitation Learning` `ROS` `MORAI`

<p align="center">
  <a href="https://github.com/libok03/VLA_Driving">
    <img src="https://raw.githubusercontent.com/libok03/VLA_Driving/main/assets/morai_current/tcp_state_drive_stop_avoid.gif" width="720" alt="TCP open-loop recorded-bag replay showing DRIVE, STOP, and AVOID predictions">
  </a><br>
  <sub>DRIVE / STOP / AVOID predictions · recorded-bag open-loop replay</sub>
</p>

Adapted **Trajectory-guided Control Prediction (TCP)** to MORAI: front-camera images, vehicle speed, and route conditions produce future waypoints and vehicle control.

- **0.2924 m ADE / 0.5225 m FDE @ 2 s** on the held-out test.
- **100% completion across 4 evaluated laps**, with **0.55 m RMSE** using TCP direct control.
- **11.02 ms mean / 18.05 ms p95** neural inference latency.
- Camera-timestamp dataset alignment, human/teacher data preparation, training, evaluation, and ROS runtime integration.

**My contribution:** learning-model development, data collection and labeling, training and inference pipelines, and runtime integration. Earlier multimodal planner experiments are also retained in the repository.

<details>
<summary>System context and contribution boundaries</summary>

The broader vehicle system combines localization, route conditioning, and an independent Safety Monitor. The repository primarily provides TCP data conversion, training/evaluation, and earlier planner experiments; it does not contain the complete deployable vehicle stack.

MPC and local-route modules were implemented by other team members.  
[Team system repository →](https://github.com/libok03/ACCA2026)

</details>


---

### SO-101: planning to physical motion
[**SO-101 Teleoperation & MoveIt 2 →**](https://github.com/libok03/maker_fair_2026_teleoperation_lerobot)  
`ROS 2 Humble` `MoveIt 2` `LeRobot` `Gazebo Harmonic` `ros2_control`

<p align="center">
  <a href="https://github.com/libok03/maker_fair_2026_teleoperation_lerobot">
    <img src="https://raw.githubusercontent.com/libok03/maker_fair_2026_teleoperation_lerobot/main/assets/so101-moveit-demo.gif" width="720" alt="MoveIt 2 planned motion executed by the physical SO-101 follower with measured joint-state feedback in RViz">
  </a><br>
  <sub>MoveIt 2 plan → physical SO-101 follower → measured joint feedback in RViz</sub>
</p>

Connecting motion planning to a physical **5-axis arm + gripper**, with feedback from **6 STS3215 servos**.

- Gazebo simulation, URDF/Xacro, MoveIt 2 configuration, and physical follower execution.
- **3 planning pipelines:** OMPL, Pilz, and STOMP.
- Motor setup and calibration tools, trajectory execution, and measured joint-state feedback.
- Ongoing work: teleoperation and demonstration-data workflows; intermittent gripper voltage alarms remain under investigation.

## Research Interests

My interests center on **robot learning and control**, **multimodal robot learning**, and **efficient AI for physical systems**. I am particularly interested in how perception and learned policies connect to planning and execution, and am exploring vision-language-action models and sim-to-real workflows.

## Technical Experience

| Area | Tools & experience |
| :--- | :--- |
| Languages & learning | Python · C++ · PyTorch · TensorRT · CUDA |
| Robotics & control | ROS / ROS 2 · MoveIt 2 · Gazebo · MPC · PID · State Machines · Path Planning |
| Perception & sensing | RF-DETR · YOLO · OpenCV · Camera · LiDAR · IMU · GNSS |
| Systems | Linux · Git · Docker |

## Team & Leadership

**President · ACCA, Soongsil University · 2026**

- Coordinated robotics and autonomous-system projects.
- Managed integration work across perception, localization, planning, control, and learning.
- Organized real-robot and simulation experiments.

<p align="center">
  <img src="assets/acca_team.jpg" width="620" alt="ACCA team at Soongsil University">
  <br><sub>ACCA team, Soongsil University</sub>
</p>

## Other Engineering & Learning Experiments

[UR5e simulation & pick-and-place](https://github.com/libok03/ros2_SimRealRobotControl) ·
[PPO Swing-Up](https://github.com/libok03/PPO_SwingUp) ·
[Atari DQN](https://github.com/libok03/Atari_DQN_Agent) ·
[CartPole RL](https://github.com/libok03/CartPole_RL)

---

## Contact

**Kang MyeongJin · 강명진**  
[markpiano01@gmail.com](mailto:markpiano01@gmail.com) · [@libok03](https://github.com/libok03)
