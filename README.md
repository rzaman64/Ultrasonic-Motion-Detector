**Raspberry Pi Motion Sensor using Ultrasonic Sensor**

**Overview**
This project uses a Raspberry Pi in combination with an HC-SR04 ultrasonic sensor to create a simple motion detection system. 
The system measures distances using ultrasonic ranging and detects motion by analyzing fluctuations in the measured distance. 
When motion is detected, an LED indicator is triggered.

**Purpose**
The purpose of this project is to create a basic motion sensor system using affordable components and basic programming. 
It demonstrates real-world applications of using sensors with Raspberry Pi for distance measurement, motion detection, and 
alerting mechanisms like an LED.

**Features**
- This project uses an HC-SR04 ultrasonic sensor to measure distance.
- Detects motion based on fluctuations in distance readings.
- LED indicator lights up when motion is detected.
- Modular and scalable code for further enhancements.

**Requirements**
- Hardware:
    - Raspberry Pi (any model with GPIO support)
    - HC-SR04 Ultrasonic Sensor
    - 1 LED
    - Jumper wires and a breadboard
- Software:
    - Python 3.x
    - RPi.GPIO library

**Installation**
1. Clone the project repository or download the project files
     ```
     git clone https://github.com/rzaman64/rpi-motion-sensor.git
     ```
2. Install the required Python  libraries if not already available:
   ```
   sudo apt-get install python-rpi.gpio
   ```

***How to Run the Code***
1. Connect the components as described in the Hardware Setup section.
2. Navigate to the project directory in the terminal.
   ```cd rpi-motion-sensor```
3. Run the UltrasonicMotionSensor.py script
   ```python3 UltrasonicMotionSensor.py```

***Hardware Setup***
- **Trig Pin** of HC-SR04 connected to GPIO Pin 16 on the Raspberry Pi.
- **Echo Pin** of HC-SR04 connected to GPIO Pin 18.
- LED connected to GPIO Pin 15, with the anode connected through a resistor.
- Ensure that the ground (GND) pins are connected to the Raspberry Pi's GND.

***Code Explanation***
The Python code works as follows:
- The Raspberry Pi triggers the ultrasonic sensor, which sends out an ultrasonic pulse.
- The pulse reflects off an object, and the sensor measures the time it takes for the pulse to return.
- The code calculates the distance of the object based on this time.
- If the distance fluctuates beyond a defined threshold (indicating motion), the LED lights up.
- The LED turns off when the object becomes stationary (i.e., distance remains consistent within the threshold).

***How it Works***
1. The sensor measures distance and continuoisly checks for any significant changes.
2. If the distance changes significantly (i.e., motion is detected), the LED lights up.)
3. The LED remains lit until the object stays within a 2cm range of the last recorded position.

***Customization***
You can customize the following variables in the code:
    - **MOTION_THRESHOLD:** Adjust the sensativity of motion detection by changing the threshold for distance fluctuations.
    - **LED Pin:** If you're using a difference GPIO pin for the LED, modify the ledPin variable in the code.

***Lessons Learned***
This project provided insights into:
    - Understanding how ultrasonic sensors work.
    - Utilizing Raspberry Pi GPIO pins for input and output.
    - Implementing motion detection with basic logic.
    - Debugging hardware and software integration issues.

***Future Improvements
- Add a buzzer or other alert mechanisms when motion is detected
- For future development, you could mention the use of **LiDAR (Light Detection and Ranging)** technology as a higher-precision alternative to the ultrasonic sensor. LiDAR can measure distances over a longer range and with greater accuracy. Here's a concise mention for the "Future Improvements" section of your README:

---

***Future Improvements***
- **Upgrade to LiDAR**: Instead of using an ultrasonic sensor, future versions of this project could integrate a LiDAR module. LiDAR provides higher precision and can detect objects at a much greater distance, making it ideal for applications requiring long-range detection and better accuracy.

***Contributing***
If youd like to contribute, feel free to submit pull requests or open issues for discussion.
   
