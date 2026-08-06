<h1>DADO ELETRONICO COM SENSOR ULTRASSONICO E SERVOMOTOR</h1>

<p>Imagem:</p>
<img width="1920" height="848" alt="Copy of Bodacious Fyyran-Snicket" src="https://github.com/user-attachments/assets/2ec9cf94-2bcc-4fd7-91e3-316e765fc695" />

---
<p>código: </p>

```
#include <Servo.h>

Servo servo1;

// PIN IDENT
int pinoLed1 = 6;
int pinoLed2 = 7;
int pinoLed3 = 8;
int pinoLed4 = 9;
int pinoLed5 = 10;
int pinoLed6 = 11;
int pinoLed7 = 5;

const int sensorPin = A0;
const int servoPin = 12;

// VAR IDENT
long Centimetro;
int numeroSorteado;

// SENSOR
long readUltrassonicDistance(int triggerPin, int echoPin)
{
  pinMode(triggerPin, OUTPUT);
  digitalWrite(triggerPin, LOW);
  delayMicroseconds(2);

  digitalWrite(triggerPin, HIGH);
  delayMicroseconds(10);

  digitalWrite(triggerPin, LOW);

  pinMode(echoPin, INPUT);

  return pulseIn(echoPin, HIGH);
}

// SETUP
void setup()
{
  Serial.begin(9600);

  servo1.attach(servoPin);
  servo1.write(0);

  // LEDS OUT
  pinMode(pinoLed1, OUTPUT);
  pinMode(pinoLed2, OUTPUT);
  pinMode(pinoLed3, OUTPUT);
  pinMode(pinoLed4, OUTPUT);
  pinMode(pinoLed5, OUTPUT);
  pinMode(pinoLed6, OUTPUT);
  pinMode(pinoLed7, OUTPUT);

  // SORT
  randomSeed(analogRead(A1));
}

// LOOP
void loop()
{

  Centimetro = 0.01723 * readUltrassonicDistance(sensorPin, sensorPin);

  if (Centimetro < 40)
  {
    numeroSorteado = random(1, 7);

    Serial.print("Numero sorteado: ");
    Serial.println(numeroSorteado);

    // EXIBE
    sorteia(numeroSorteado);

    // IF PAR
    if (numeroSorteado % 2 == 0)
    {

      servo1.write(90);

      delay(2000);

      servo1.write(0);

      delay(2000);
    }
    else
    {
      delay(2000);
    }
  }

  delay(100);
}


// EXIBIÇÃO
void sorteia(int numero)
{
  // RESET
  digitalWrite(pinoLed1, LOW);
  digitalWrite(pinoLed2, LOW);
  digitalWrite(pinoLed3, LOW);
  digitalWrite(pinoLed4, LOW);
  digitalWrite(pinoLed5, LOW);
  digitalWrite(pinoLed6, LOW);
  digitalWrite(pinoLed7, LOW);


  //1
  if (numero == 1)
  {
    digitalWrite(pinoLed7, HIGH);
  }


  //2
  if (numero == 2)
  {
    digitalWrite(pinoLed1, HIGH);
    digitalWrite(pinoLed6, HIGH);
  }


  //3
  if (numero == 3)
  {
    digitalWrite(pinoLed3, HIGH);
    digitalWrite(pinoLed7, HIGH);
    digitalWrite(pinoLed4, HIGH);
  }


  //4
  if (numero == 4)
  {
    digitalWrite(pinoLed1, HIGH);
    digitalWrite(pinoLed3, HIGH);
    digitalWrite(pinoLed4, HIGH);
    digitalWrite(pinoLed6, HIGH);
  }


  //5
  if (numero == 5)
  {
    digitalWrite(pinoLed1, HIGH);
    digitalWrite(pinoLed3, HIGH);
    digitalWrite(pinoLed6, HIGH);
    digitalWrite(pinoLed7, HIGH);
    digitalWrite(pinoLed4, HIGH);
  }


  //6
  if (numero == 6)
  {
    digitalWrite(pinoLed1, HIGH);
    digitalWrite(pinoLed2, HIGH);
    digitalWrite(pinoLed3, HIGH);
    digitalWrite(pinoLed5, HIGH);
    digitalWrite(pinoLed6, HIGH);
    digitalWrite(pinoLed4, HIGH);
  }

  delay(2000);


  // RERESET
  digitalWrite(pinoLed1, LOW);
  digitalWrite(pinoLed2, LOW);
  digitalWrite(pinoLed3, LOW);
  digitalWrite(pinoLed4, LOW);
  digitalWrite(pinoLed5, LOW);
  digitalWrite(pinoLed6, LOW);
  digitalWrite(pinoLed7, LOW);
}
```
