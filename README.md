# wristband-healthy-monitoring
my personal project
**A. Architecture & component selection**
1. Describe the role of ESP32 in the system and the reasons for choosing it (Wi-Fi/BLE, power, peripherals).
- The role of esp32 has wifi connection, 5V DC power, I2C protocol

2. Describe the SpO₂ & heart rate measurement principle of MAX30100 (PPG, LED/photodiode, motion noise filtering).

- MAX30100 measures SpO₂ and heart rate by emitting red (660nm) and infrared (940nm) light through the tissue, then measuring the amount of reflected light with a photodetector. Oxidized and deoxygenated hemogoblin absorb these two wavelengths differently, allowing calculation of blood oxygen concentration (SpO₂) based on the ratio of red/infrared light. Heart rate is determined by detecting changes in blood flow with each beat, based on the fluctuations in the amount of light measured

3. State the MPU6050 function (accelerometer/gyro) and the axes of interest when detecting falls/dizziness.
- MPU6050 detects abnormal movements during movement such as falls. All 3 axes need to be measured and all 3 axes combined when measuring.

4. LM35 measures analog temperature: - requires ADC of ESP32 and corresponding anti-interference.
5. Design a voltage divider circuit to measure 3.7V Li-ion battery, calculate the resistance to ensure it does not exceed Vref ADC.

**B. Mechanical design & wearability** 
1. Factors affecting the quality of PPG signal when worn on the wrist (pressure, position, skin color, movement).
- Non-standard wearing methods will affect the heart rate value, such as light leakage due to poor fit, arm swinging, and slight movement of the watch on the skin.
- The watch is worn close to the joint, which will interfere with the heart rate signal. Wearing the watch too tight, lifting the arm, and clenching the hand will also affect the blood circulation and heart rate signals
- Sweat stains on the watch may interfere with its heart rate measurement accuracy. When sweat accumulates on the watch sensors, it may create a barrier between the skin and the sensors, resulting in inaccurate or inconsistent heart rate
2. Due to the characteristics of the PPG chip, the blood oxygen (red light) and heart rate (green light) cannot be turned on at the same time, that is, the blood oxygen and heart rate cannot be measured at the same time. If the blood oxygen measurement is continuous for a long time, there will be no background heart rate monitoring data during this period.
3. Criteria for selecting the strap/module size for durability and breathability. Rubber strap/size fits the user's hand.
4. Solution to reduce vibration and block ambient light to the SpO₂ sensor. Tightly worn, raised plastic design to fit the user's hand

  Testing picture:
  <img width="720" height="1280" alt="ảnh" src="https://github.com/user-attachments/assets/2646016e-0e82-4419-9548-a82953f94ae8" />

information:
phone: +84 964 677 276
mail: duckphann@gmail.com
