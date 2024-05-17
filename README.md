# PhotoresistorLED
void setup() {
  // put your setup code here, to run once:
  pinMode(9,OUTPUT);
  Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:
  int sensorRead=analogRead(A0);
  Serial.println(sensorRead);
  if (sensorRead<450)sensorRead=450;
  else if (sensorRead>880)sensorRead=880;
  int ledblink=map(sensorRead,450,880,0,665);
  analogWrite(9,sensorRead);
  delay(1);
}
