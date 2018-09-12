# Labyrinth-12092018
 //Labyrinth koodi, Robot Uprising 2018, L.K. & P.Y.
int buttonPin = 2; //Painike jolla labyrintti liikkuu
int buttonState = 0; //Painikkeen alkutila

int forwardPin =  5; //Lineaarimoottori eteen
int backPin =  6; //Lineaarimoottori taakse

void setup() {

pinMode(forwardPin, OUTPUT);
pinMode(backPin, OUTPUT);
pinMode(buttonPin, INPUT);
}

void loop(){

  buttonState = digitalRead(buttonPin);
  if (buttonState == HIGH){
    digitalWrite(forwardPin, HIGH);
    delay(3000);
    digitalWrite(forwardPin, LOW);
    delay(5000);
    digitalWrite(backPin, HIGH);
    delay(3000);
    digitalWrite(backPin, LOW);
    while (digitalRead(buttonPin))delay(1); //odotetaan että nappi ei ole enää pohjassa, ennen kuin jatketaan eteenpäin
  }
  else{
    digitalWrite(forwardPin, LOW);
    digitalWrite(backPin, LOW);
  }
}
