# tej3m-2-06-Arduino
/*
 * HC-SR04 example sketch
 *
 * https://create.arduino.cc/projecthub/Isaac100/getting-started-with-the-hc-sr04-ultrasonic-sensor-036380
 *
 * by Isaac100
 */

const int TRIGPIN = 9;
const int ECHOPIN = 10;

float duration, distance;

void setup() {
  pinMode(TRIGPIN, OUTPUT);
  pinMode(ECHOPIN, INPUT);
  Serial.begin(9600);
}

void loop() {
  digitalWrite(TRIGPIN, LOW);
  delayMicroseconds(2);
  digitalWrite(TRIGPIN, HIGH);
  delayMicroseconds(10);
  digitalWrite(TRIGPIN, LOW);

  duration = pulseIn(ECHOPIN, HIGH);
  distance = (duration*.0343)/2;
  Serial.print("Distance: ");
  Serial.println(distance);
  delay(100);
}
