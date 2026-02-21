# 🤖 STM32-Based 4-DOF Robotic Arm

An embedded systems project implemented in C using the **STM32F103C8T6 (Blue Pill)** microcontroller to control a 4-DOF servo-actuated robotic arm capable of:

- Pick-and-place operations
- Alphabet writing (e.g., writing letter "A")
- Smooth servo motion using PWM

---

## 📁 Repository Structure

```
Robotic-arm/
├── object.c              # Pick-and-place control logic
├── write.c               # Alphabet writing (trajectory control)
├── poster.pdf            # Academic project poster
├── es_project_video.mp4  # Demo video
└── README.md             # Project documentation
```

---

## 📖 Project Overview

This project implements a servo-controlled robotic arm using hardware-level register programming on the STM32 platform.

The system:
- Generates **50 Hz PWM signals** using Timer2
- Controls **4 servo motors** (Base, Shoulder, Elbow, Gripper)
- Implements **smooth movement** using incremental angle transitions
- Demonstrates **object manipulation** and **handwriting automation**

This project demonstrates core embedded concepts including:
- PWM (Pulse Width Modulation)
- Timer configuration
- Direct register programming
- Multi-servo coordination
- Motion sequencing algorithms

---

## ⚙️ Hardware Configuration

| Component | Description |
|-----------|-------------|
| Microcontroller | STM32F103C8T6 (Blue Pill) |
| Timer Used | TIM2 (4 PWM Channels) |
| Servo Motors | SG90 / MG90S |
| Channels Used | PA0–PA3 (TIM2 CH1–CH4) |
| Power Supply | External 5V (2A recommended) |
| Programmer | ST-Link V2 |

---

## 🔌 Servo Mapping

| Servo | Pin | Timer Channel | Function |
|-------|-----|---------------|----------|
| Base | PA0 | TIM2_CH1 | Horizontal rotation |
| Gripper | PA1 | TIM2_CH2 | Open/Close |
| Shoulder | PA2 | TIM2_CH3 | Vertical lift |
| Elbow | PA3 | TIM2_CH4 | Arm extension |

---

## ✍️ Functional Features

### 🔹 Pick and Place
- Base rotation control
- Shoulder & elbow coordinated motion
- Gripper open/close logic
- Smooth movement using incremental angle stepping

### 🔹 Alphabet Writing
- Trajectory-based motion control
- Coordinated base + shoulder motion
- Controlled pen lift and placement
- Demonstrated writing of letter **"A"**

---

## 🛠️ Software Architecture

### 1️⃣ PWM Initialization
- Timer2 configured at **50 Hz**
- Prescaler: `72`
- ARR: `20000`
- PWM Mode 1 enabled on all 4 channels

### 2️⃣ Servo Angle Conversion

```c
pulse = 350 + ((angle * 2300) / 180);
```

Converts angle (0–180°) to pulse width (µs).

### 3️⃣ Smooth Movement Logic

Gradual angle stepping for fluid motion:

```c
for(i = from; i <= to; i++)
    Servo_SetAngle(ch, i);
```

---

## 🚀 Getting Started

### Clone Repository

```bash
git clone https://github.com/navadeep555/Robotic-arm.git
cd Robotic-arm
```

### Flash to STM32

1. Open project in **STM32CubeIDE**
2. Connect **ST-Link V2** to your Blue Pill board
3. Build the project (`Project → Build All`)
4. Flash to board (`Run → Debug` or `Run → Run`)
5. Provide an **external 5V / 2A supply** to the servo motors

---

## 🎥 Demo

A demonstration video is included in the repository: [`es_project_video.mp4`](./es_project_video.mp4)

Shows:
- Pick-and-place operation
- Alphabet writing demonstration

---

## 📄 Project Poster

Academic documentation and system design overview: [`poster.pdf`](./poster.pdf)

Includes:
- Block diagram
- Hardware architecture
- Software flow
- Results and conclusions

---

## 📚 Learning Outcomes

This project demonstrates practical understanding of:
- Embedded C programming
- Direct hardware register manipulation
- PWM signal generation
- Real-time motion control
- Multi-servo synchronization
- Mechanical-electrical integration

---

## 🤝 Authors & Contributors

| Name | GitHub |
|------|--------|
| **Navadeep** | [@navadeep555](https://github.com/navadeep555) |
| **Kukkadapu Datta** | [@datta0312](https://github.com/datta0312) |
| **Masannagari Nandan Reddy** | [@nandanreddy386](https://github.com/nandanreddy386) |
| **K Srivarshith** | [@varshith2326](https://github.com/varshith2326) |

---

## 📜 License

This project is developed for **academic purposes**. For commercial use, please contact the authors.
