🤖 4-DOF Servo-Actuated Robotic Arm

Design and Implementation of a 4-DOF Robotic Arm for Object Manipulation and Writing Applications

🧠 Overview

This project implements a 4-DOF robotic arm capable of picking and placing objects, performing simple writing motions, and demonstrating coordinated servo control.
The arm is powered by the STM32F103C8T6 (Blue Pill) microcontroller and controlled using TowerPro SG90 servo motors. PWM signals are generated through Timer 2 to control the base, shoulder, elbow, and gripper movements.

⚙️ Hardware Components

🟦 STM32F103C8T6 (Blue Pill)

⚙️ TowerPro SG90 Servo Motors (x4)

Base

Shoulder

Elbow

Gripper

🔌 5V 2A Power Adapter

🧩 Breadboard and jumper wires

🖲️ ST-LINK/V2 Programmer

🔌 Pin Configuration
Servo Motor	STM32 Pin	TIM2 Channel
Base	PA0	TIM2_CH1
Gripper	PA1	TIM2_CH2
Shoulder	PA2	TIM2_CH3
Elbow	PA3	TIM2_CH4
🧾 Features

✅ 4-DOF motion control (Base, Shoulder, Elbow, Gripper)
✅ Smooth servo movement with gradual PWM changes
✅ Object pick-and-place automation
✅ Capability to perform simple writing tasks (e.g., alphabet “N”)
✅ Low-cost and embedded-friendly design

💻 Software

IDE: Keil µVision / STM32CubeIDE

Language: C

Timer: TIM2 configured for 50Hz PWM output (20ms period)

Clock: 72 MHz system clock

🧩 How It Works

Initialization: Sets all servos to neutral position.

Pick Phase: Moves shoulder and elbow downward, opens gripper, then closes to hold an object.

Place Phase: Lifts object up, rotates base, and releases object.

Writing Phase: Moves joints in sequence to trace alphabet "N".

▶️ Running the Code

Connect the servos as per the pin configuration.

Flash the code to the STM32 Blue Pill using ST-LINK/V2.

Power the board and servo motors (5V, 2A recommended).

Observe automatic motion sequence.

📁 Folder Structure
📁 Robotic_Arm_Project/
│
├── 📄 README.md
│
├── 📂 Code/
│   ├── object.c          # Code for object picking and placing
│   ├── write.c           # Code for writing alphabet (e.g., N)
│   ├── main.c            # Combined control code (optional)
│
├── 📂 Media/
│   ├── es_project_arm_video.mp4   # Demo video of arm operation
│   └── poster.pdf            

🎯 Future Improvements

Joystick or Bluetooth-based manual control

Object detection using IR or camera module

Path planning for complex writing and drawing

🧑‍💻 Contributors

Syamala & Team
Guided by: [Your Faculty/Guide Name]
Department of Electronics and Communication Engineering
[Your College Name]

📜 License

This project is released under the MIT License – feel free to use and modify it for educational purposes.
