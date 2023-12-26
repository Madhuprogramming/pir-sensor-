# pir-sensor-
This repository contains Arduino code for interfacing a PIR (Passive Infrared) sensor with an Arduino board. The PIR sensor is used to detect motion and trigger actions based on the presence of movement.
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
