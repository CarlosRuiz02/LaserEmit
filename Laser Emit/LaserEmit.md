## Laser Emit

Un diodo láser es un dispositivo similar a un LED convencional, pero que en lugar de emitir luz convencional emite un haz de láser.

Como sabemos, a diferencia de un haz de luz convencional un haz de láser avanza en línea recta. Si el generador láser fuera perfecto y el haz estuviera en el vacío, la luz seguiría su camino hasta que encontrara un obstáculo.

### Hardware utilizado en este tutorial:
<ul>
<li>1 x ESP-WROOM-32 Dev Module</li>
<li>1 x Micro USB Cable</li>
<li>1 x Protoboard</li>
<li>3 x Cables hembra</li>
<li>2 x Cables macho</li>
</ul>

## Sensor
![](https://github.com/CarlosRuiz02/LightBlocking/blob/main/Light%20Blocking/Light%20Blocking%20sensor.webp)
## Diagrama
![](https://github.com/CarlosRuiz02/LightBlocking/blob/main/Light%20Blocking/Light%20blocking%20Diagrama.PNG)

**Nota 1: El sensor del diagrama es diferente pero la conexión es exactamente la misma**


**Nota 2: Cambiar el pin del LED al 5**

## Código
```c++
int LedOutput = 5;// Define as LED Output Pin 5
int SensorPin = 12; // Define as Sensor Pin Input
int Value;// Define as variable 
void setup(){
    Serial.Begin(115200);
    pinMode(LedOutput,OUTPUT);//Set as LedOutput
    pinMode(SensorPin,INPUT);//Set as photo interrupter sensor output interface
}
void loop(){
    Value=digitalRead(SensorPin);// Set as sensor read SensorPin 
    if(Value==HIGH){ //If value is equal to HIGH estate then turn LED output = high
        digitalWrite(LedOutput,HIGH); // Set LedOutPut to HIGH or ON
        Serial.print("Sensor Bloqueado\n");
    }else{
        digitalWrite(LedOutput,LOW); // Set LedOutPut to LOW or OFF
        Serial.print("Sin Obstrucción\n");
    }
}