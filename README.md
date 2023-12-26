# pir-sensor-
This repository contains Arduino code for interfacing a PIR (Passive Infrared) sensor with an Arduino board. The PIR sensor is used to detect motion and trigger actions based on the presence of movement.


Overview:
This project demonstrates how to connect a PIR sensor to an Arduino board and use it to detect motion. The Arduino code included in this repository reads the sensor data and provides a simple output based on the detected motion.

Hardware Requirements:

Arduino Board (e.g., Arduino Uno)
PIR Sensor
Jumper Wires

Setup Instructions:

Clone or download this repository.
Connect the PIR sensor to the Arduino board following the wiring diagram.
Upload the Arduino code to the board using the Arduino IDE.
Open the serial monitor to view the output based on motion detection.

CODE:
// Define the PIR sensor pin
int pirSensorPin = 2;  // Change this to the actual pin you have connected the sensor to

void setup() {
  Serial.begin(9600);  // Initialize Serial communication
  pinMode(pirSensorPin, INPUT);  // Set the PIR sensor pin as INPUT
}

void loop() {
  // Read the state of the PIR sensor
  int pirState = digitalRead(pirSensorPin);

  // Check if motion is detected
  if (pirState == HIGH) {
    Serial.println("Motion detected!");
    // You can add additional actions or functions here
    delay(500);  // Add a delay to avoid multiple detections within a short time
  } else {
    Serial.println("No motion detected.");
  }
  
  delay(100);  // Adjust the delay based on your application's needs
}
