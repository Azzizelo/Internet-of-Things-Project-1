//Pin Definitions
int soundSensorPin = A0; //Analog Pin for sound sensor 
int buzzerPin = 3; // Digital pin for buzzer

int threshold = 500; //Adjust according to sound sensor sensitivity

void setup() {
//initialize the buzzer pin as an output
pinMode(buzzerPin, OUTPUT);
//initialize the serial monitor for debugging
Serial.begin(9600);
}

void loop() {
//Read value from the sound sensor 
int soundValue - analogRead(soundSensorPin);

//Print the Sound Value to the serial monitor for debugging
Serial.println(soundValue);

//check if the sound value to exceeeds the threshold
if ( soundValue > threshold) {
//Turn on the buzzer if sound is detected above the threshold
digitalWrite(buzzerPin, HIGH);
} else {
//turn off the buzzer if sound is below the threshold
digitalWrite(buzzerPin, LOW);
}

//Small delay to avoid overwhelming the serial monitor 
delay(100);
}
