![header](https://capsule-render.vercel.app/api?type=waving&color=0:0f2027,50:203a43,100:2c5364&height=280&section=header&text=Kang%20MyeongJin&fontSize=60&fontColor=ffffff&animation=fadeIn&fontAlignY=35&desc=Robotics%20Engineer%20%7C%20Control%20Theory%20%7C%20Reinforcement%20Learning&descAlignY=55&descAlign=50)

<p align="center">
  <a href="mailto:markpiano01@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white"/></a>
  <a href="https://libok03.github.io"><img src="https://img.shields.io/badge/Blog-000000?style=for-the-badge&logo=github&logoColor=white"/></a>
</p>

<p align="center">
  <b>고정밀 제어 알고리즘 및 물리적 AI(Physical AI) 연구</b><br/>
  숭실대학교 자율주행 팀 <b>ACCA 회장</b>으로서,<br/>
  비선형 시스템의 <b>최적 제어(Optimal Control)</b>와 <b>강인한 의사결정 구조</b> 설계를 연구하고 있습니다.
</p>

---

## 🛠️ Advanced Engineering & Research

단순 기능을 넘어 시스템의 **수학적 모델의 정밀도**와 **제어 안정성(Stability)** 확보를 최우선으로 연구한 핵심 성과입니다.

* **Constrained Optimal Control (MPC)**: Kinematic Bicycle Model 기반의 **MPC**를 설계하여 차량의 비선형 동역학을 고려한 최적 경로 추종을 구현했습니다. [cite_start]특히, Solver의 수렴성 실패에 대비한 **Heuristic Fallback(Stanley)** 기구축을 통해 시스템의 고가용성을 확보했습니다. [cite: 146, 150]
* **Hierarchical Behavioral Planning**: 복잡한 동적 환경에서의 의사결정을 위해 **Hierarchical FSM**을 설계했습니다. [cite_start]상태 천이(State Transition) 과정에서의 불연속성을 최소화하기 위해 3차 보간법(Cubic Spline) 기반의 전역 경로 완화 기법을 적용했습니다. [cite: 140, 215]
* [cite_start]**Stochastic Perception Filtering**: 센서 노이즈 및 오인식으로 인한 급격한 제어 입력을 방지하기 위해, 인식 데이터의 시공간적 일관성(Temporal Consistency)을 검증하는 필터링 알고리즘을 도입하여 제어 명령의 평활도(Smoothing)를 개선했습니다. [cite: 243]
* **Reinforcement Learning for Underactuated Systems**: PPO(Proximal Policy Optimization) 알고리즘을 활용하여 **Inverted Pendulum Swing-up** 제어를 구현했습니다. 보상 함수(Reward Function) 설계를 통해 복잡한 물리 시스템의 제어 전략을 학습 기반으로 최적화하는 연구를 수행 중입니다.

## 🚗 Key Projects

| Project | Description | Tech Stack |
| :--- | :--- | :--- |
| **[ACCA_2025](https://github.com/libok03/ACCA_2025)** | **Autonomous Driving Architecture** <br> FSM 기반 미션 수행 및 MPC/Stanley 제어기 구축 | ![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=c%2B%2B&logoColor=white) ![ROS2](https://img.shields.io/badge/ROS2-22314E?style=flat-square&logo=ros&logoColor=white) |
| **[PPO_SwingUp](https://github.com/libok03/PPO_SwingUp)** | **RL: Policy Optimization** <br> PPO 알고리즘 기반 Underactuated 시스템 제어 최적화 | ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white) |
| **[ros2_SimReal](https://github.com/libok03/ros2_SimRealRobotControl)** | **Sim-to-Real Manipulation** <br> Gazebo 환경과 실제 UR5e 매니퓰레이터 간 정밀 제어 구현 | ![ROS2](https://img.shields.io/badge/ROS2-22314E?style=flat-square&logo=ros&logoColor=white) ![MoveIt2](https://img.shields.io/badge/MoveIt2-3C9ED5?style=flat-square) |
| **[CartPole_RL](https://github.com/libok03/CartPole_RL)** | **Physical System Control** <br> DQN/PPO 비교를 통한 물리 시스템의 밸런싱 제어 연구 | ![RL](https://img.shields.io/badge/RL-Reinforcement--Learning-blueviolet?style=flat-square) ![Gym](https://img.shields.io/badge/OpenAI_Gym-2ECC71?style=flat-square) |

## 🧠 Technical Proficiency

**Optimal Control & RL**
<img src="https://img.shields.io/badge/MPC-E74C3C?style=for-the-badge&logoColor=white"/> <img src="https://img.shields.io/badge/PPO / RL-8E44AD?style=for-the-badge&logoColor=white"/> <img src="https://img.shields.io/badge/LQR / PID-3498DB?style=for-the-badge&logoColor=white"/>

**Robotics Framework**
<img src="https://img.shields.io/badge/ROS2-22314E?style=for-the-badge&logo=ros&logoColor=white"/> <img src="https://img.shields.io/badge/MoveIt2-3C9ED5?style=for-the-badge&logoColor=white"/> <img src="https://img.shields.io/badge/Gazebo / Unity-F58220?style=for-the-badge&logo=gazebosim&logoColor=white"/>

**Languages & Tools**
<img src="https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white"/> <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"/> <img src="https://img.shields.io/badge/MATLAB-007672?style=for-the-badge&logo=mathworks&logoColor=white"/> <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white"/>

---

## 🎯 Research Interests
🤖 Control Theory       — Nonlinear MPC, Optimal Control, Adaptive Control<br/>
🧠 Physical AI          — Deep Reinforcement Learning for Real-world Deployment<br/>
🛤️ Motion Planning      — Sampling-based & Optimization-based Path Planning<br/>

---

## 📝 Selected Technical Log

- [UR5e + Robotiq: 비선형 환경에서의 충돌 회피(SRDF) 및 경로 최적화](https://libok03.github.io/dev%20log/2026/02/04/moveit2-%EC%8B%9C%ED%96%89%EA%B8%B0.html)
- [MPC Solver Optimization: 비선형 구속 조건 하에서의 실시간 제어 성능 분석](https://libok03.github.io/dev%20log/2026/02/04/gazebo-moveit-%ED%97%9B%EA%B3%A0%EC%83%9D.html)
- [Stochastic Control: PPO 보상 함수 설계를 통한 언더액추에이티드 시스템 제어 전략](https://libok03.github.io/dev%20log/2026/02/03/gazebo-moveit2-%EC%97%B0%EA%B2%B0%EC%8B%9C%EB%8F%84.html)
![footer](https://capsule-render.vercel.app/api?type=waving&color=0:0f2027,50:203a43,100:2c5364&height=120&section=footer)
