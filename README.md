
# IOT
1.Led:https://wokwi.com/projects/333796636268429907<br>
2.three led:https://wokwi.com/projects/333797944251646547<br>
3.Arduino RGB LED:https://wokwi.com/projects/333799378069226066<br>
                  https://wokwi.com/projects/333805648701555283<br>
4.LCD:https://wokwi.com/projects/334433515082875475<br>
5.ultrasonic:https://wokwi.com/projects/334345224284275284<br>
6.temperature;https://wokwi.com/projects/334346231606149714<br>
7.PIR:https://wokwi.com/projects/334347041012449875<br>
8.IR sensor:https://wokwi.com/projects/334347782067323474<br>
9.button led:https://wokwi.com/projects/334431013706924626<br>
10.led fade:https://wokwi.com/projects/334431225002328659<br>
11.MOtion Sensor:https://wokwi.com/projects/334431854492910163<br>
12)Motion Sensor Buzzer:https://wokwi.com/projects/334433831716127314<br>
13)Ultra Sonic sensor LED:https://wokwi.com/projects/334434440478458452 <br>
14)servo motor controlled by potentiometer:https://wokwi.com/projects/334977104366010964<br>
15)servo motor :https://wokwi.com/projects/334976377748980307<br>
16)servo motor with button:https://wokwi.com/projects/334977486870807124<br>
17)servo motor with ultrasonic sensor:https://wokwi.com/projects/334981639074480722<br>
18)buzzer using button:https://wokwi.com/projects/335071789621183058<br>
19)buzzer with beep:https://wokwi.com/projects/335066692974543442<br>
20).Buzzer with ultrasonic sensor:https://wokwi.com/projects/335609324460048978<br>
21)ultrasonic sensor with buzzer and LED at 20cm:https://wokwi.com/projects/335611089367597652<br> 

ZA
 void loop()<br> {<br>
   // put your main code here, to run repeatedly:<br>
   int irvalue=digitalRead(ir);<br>
   if(irvalue==LOW)<br>
   {<br>
     Serial.println("LOW");<br>
     digitalWrite(led,HIGH);<br>
   }<br>
   else<br>
   {<br>
     Serial.println("HIGH");<br>
     digitalWrite(led,LOW);<br>
   }<br>
 delay(100);<br>
 }<br>
</br>
</br>
</br>
     LDR<br>
     const int ldrPin=A0;<br>
     void setup() {<br>
       Serial.begin(9600);<br>
       pinMode(ldrPin,INPUT);<br>
     }<br>
     void loop()<br> {<br>
       int rawData = analogRead(ldrPin);  <br> 
       Serial.println(rawData);<br>
       delay(1000);<br>
     }<br>
</br><br>
</br><br>
</br><br>

 LDR_LED<br>

 int ldr=A0;//Set A0(Analog Input) for LDR.<br>
 int value=0;<br>
 int led=D1;<br>
 void setup()<br> {<br>
 Serial.begin(9600);<br>
 pinMode(led,OUTPUT);<br>
 }<br>

 void loop()<br> {<br>
 value=analogRead(ldr);//Reads the Value of LDR(light).<br>
 Serial.println("LDR value is :");//Prints the value of LDR to Serial Monitor.<br>
 Serial.println(value);<br>
 if(value<50)<br>
   {<br>
     digitalWrite(led,HIGH);//Makes the LED glow in Dark.<br>
   }<br>
   else<br>
   {<br>
     digitalWrite(led,LOW);//Turns the LED OFF in Light.<br>
   }<br>
   delay(1000);<br>
 }\<br>
 </br><br>
 </br><br>
 LED_CHASER<br>
 
int pinsCount=6;                        // declaring the integer variable pinsCount
int pins[] = {D0,D1,D7,D5,D3,D2};          // declaring the array pins[]

void setup() {                
  for (int i=0; i<pinsCount; i=i+1){    // counting the variable i from 0 to 9
    pinMode(pins[i], OUTPUT);            // initialising the pin at index i of the array of pins as OUTPUT
  }
}

void loop() {
  for (int i=0; i<pinsCount; i=i+1){    // chasing right
    digitalWrite(pins[i], HIGH);         // switching the LED at index i on
    delay(100);                          // stopping the program for 100 milliseconds
    digitalWrite(pins[i], LOW);          // switching the LED at index i off
  }
  for (int i=pinsCount-1; i>0; i=i-1){   // chasing left (except the outer leds)
   digitalWrite(pins[i], HIGH);         // switching the LED at index i on
    delay(100);                          // stopping the program for 100 milliseconds
    digitalWrite(pins[i], LOW);          // switching the LED at index i off

  }
}


