# Motion Detection Sensor using Arduino and PIR Sensor 🚨

An Arduino UNO-based motion detection system using a PIR (Passive Infrared) sensor. When motion is detected, an LED and buzzer alarm are triggered, with live sensor readings shown on the Serial Monitor.

## 📽️ Demo

> Add your video link here after uploading (see "Adding the Demo Video" section below).

```
[Demo Video](PASTE_VIDEO_LINK_HERE)
```

## 📌 Overview

A motion detection sensor is an electronic device used to detect movement in a specific area. This project connects a PIR sensor to an Arduino UNO to detect human motion — when movement is sensed, LEDs glow and a buzzer sounds an alarm.

## ⚙️ How It Works

1. The PIR sensor continuously monitors the surrounding area for infrared radiation emitted by human bodies or moving objects.
2. When a person moves in front of the sensor, the infrared energy changes.
3. The PIR sensor sends a signal to the Arduino UNO.
4. If no movement is detected, the green LED remains ON.
5. When motion is detected, the PIR sensor sends a HIGH signal, and the Arduino turns ON the red LED and buzzer alarm.
6. Sensor values are also displayed in real time on the Serial Monitor.

## 🧩 Components Used

| Component | Purpose |
|---|---|
| Arduino UNO | Controls the entire system |
| PIR Sensor | Detects motion |
| LEDs | Indicate motion detection |
| Buzzer | Produces alarm sound |
| Breadboard & Wires | Circuit connections |

## 🔧 Circuit Simulation

The circuit was designed and simulated in **Tinkercad**, with the PIR sensor wired to analog pin A0, LEDs on pins 6 and 7, and a buzzer/speaker on pin 10.

## 💻 Source Code

The Arduino sketch is available in [`motion_detection_sensor.ino`](./motion_detection_sensor.ino):

```cpp
int pirsensor = 0;

void setup() {
  pinMode(A0, INPUT);
  Serial.begin(9600);
  pinMode(7, OUTPUT);
  pinMode(6, OUTPUT);
  pinMode(10, OUTPUT);
}

void loop() {
  pirsensor = analogRead(A0);
  Serial.println(pirsensor);
  if (pirsensor >= 100) {
    digitalWrite(7, LOW);
    digitalWrite(6, HIGH);
    tone(10, 92, 100);
  } else {
    digitalWrite(7, HIGH);
    digitalWrite(6, LOW);
    digitalWrite(10, LOW);
  }
  delay(10);
}
```

## 📁 Repository Structure

```
motion-detection-sensor-arduino/
├── README.md
├── motion_detection_sensor.ino
├── Motion_Detection_Sensor_Report.pdf
└── demo/
    └── screen_recording_demo.mp4   (or a link to hosted video, see below)
```

## 🚀 Applications

- Security alarm systems
- Automatic lighting
- Smart homes
- Industrial automation systems

## 📄 Full Report

See [`Motion_Detection_Sensor_Report.pdf`](./Motion_Detection_Sensor_Report.pdf) for the complete project report, including circuit diagrams and detailed explanation.

## 👤 Author

Add your name, college/institution, and contact/social links here.

## 📜 License

Add a license of your choice (e.g., MIT) — see [choosealicense.com](https://choosealicense.com/) if unsure.
