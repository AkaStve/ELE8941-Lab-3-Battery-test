// ELE8941 Robotics Lab 3: Battery Part - June 3, 2026
void setup()
{

pinMode(6, OUTPUT); //DIR pin of FL wheel
pinMode(5, OUTPUT); //PWM pin of FL wheel
pinMode(44, OUTPUT); //DIR pin of FR wheel
pinMode(45, OUTPUT); //PWM pin of FR wheel
pinMode(3, OUTPUT); //DIR pin of BL wheel
pinMode(4, OUTPUT); //PWM pin of BL wheel
pinMode(48, OUTPUT); //DIR pin of BR wheel
pinMode(46, OUTPUT); //PWM pin of BR wheel

Serial.begin(9600);
delay(4000);
}
void loop()
{
//Drive forward for 3 s 
  //F. L. motor
    Serial.print("Drives forward for 3 s");
    digitalWrite(6, LOW); // DIR to pin 6
    analogWrite(5, 178); // PWM to pin 5
  //F. R. motor
    digitalWrite(44, LOW); // DIR to pin 44
    analogWrite(45, 178); // PWM to pin 45
  //B. L. motor
    digitalWrite(3, LOW); // DIR to pin 44
    analogWrite(4, 178); // PWM to pin 45
  //B. R. motor
    digitalWrite(48, LOW); // DIR to pin 44
    analogWrite(46, 178); // PWM to pin 45
    delay(3000);

  //10 s to measure the traveled distance
    Serial.print("10 s to measure the traveled distance");
    analogWrite(5, 0);
    analogWrite(45, 0);
    analogWrite(4, 0);
    analogWrite(46, 0);
    delay(10000);

//Drive backward for 3 s
  //F. L. motor
    Serial.print("Drives backward for 3 s");
    digitalWrite(6, HIGH); // DIR to pin 6
    analogWrite(5, 255); // PWM to pin 5
  //F. R. motor
    digitalWrite(44, HIGH); // DIR to pin 44
    analogWrite(45, 255); // PWM to pin 45
  //B. L. motor
    digitalWrite(3, HIGH); // DIR to pin 44
    analogWrite(4, 255); // PWM to pin 45
  //B. R. motor
    digitalWrite(48, HIGH); // DIR to pin 44
    analogWrite(46, 255); // PWM to pin 45
    delay(3000);
while(1);
}
