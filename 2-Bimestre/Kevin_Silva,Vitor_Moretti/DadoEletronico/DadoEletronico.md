# Vitor Moretti e Kevin Silva - 1ºc2
<p> Dado eletrônico que sorteia um numero aleatorio e acende leds de acordo com o numero</p>

<p> Imagem: </p>
<img width="1920" height="848" alt="Bodacious Fyyran-Snicket" src="https://github.com/user-attachments/assets/e3e56da5-dc36-4bef-a282-2cc89bfc58da" />

<p>Código: </p>

``` 
// INIT IDENT
int pinoLed1 = 7;
int pinoLed2 = 8;
int pinoLed3 = 9;
int pinoLed4 = 10;
int pinoLed5 = 11;
int pinoLed6 = 12;
int pinoLed7 = 6;
int pinoBotao = 2;

void setup() {
  pinMode(pinoLed1,OUTPUT);
  pinMode(pinoLed2,OUTPUT);
  pinMode(pinoLed3,OUTPUT);
  pinMode(pinoLed4,OUTPUT);
  pinMode(pinoLed5,OUTPUT);
  pinMode(pinoLed6,OUTPUT);
  pinMode(pinoLed7,OUTPUT);
  pinMode(pinoBotao,INPUT_PULLUP);
  randomSeed(analogRead(0));
}
// FIM IDENT

// SORTEIO
void loop() {
  if(digitalRead(pinoBotao) == HIGH) {
    sorteia();
  }
}

void sorteia() {
  int numeroSorteado = random(1,8);

  digitalWrite(pinoLed1, LOW);
  digitalWrite(pinoLed2, LOW);
  digitalWrite(pinoLed3, LOW);
  digitalWrite(pinoLed4, LOW);
  digitalWrite(pinoLed5, LOW);
  digitalWrite(pinoLed6, LOW);
  digitalWrite(pinoLed7, LOW);
  
  if(numeroSorteado==1) {
    digitalWrite(pinoLed7,HIGH);	//SE SORT=1
  }    
  
  if(numeroSorteado==2) {
    digitalWrite(pinoLed1, HIGH);	//SE SORT=2
    digitalWrite(pinoLed6, HIGH);
  }
  
  if(numeroSorteado==3) {
    digitalWrite(pinoLed3, HIGH);
    digitalWrite(pinoLed7, HIGH);	//SE SORT=3
    digitalWrite(pinoLed4, HIGH);
  }
  
  if(numeroSorteado==4) {
    digitalWrite(pinoLed1, HIGH);
    digitalWrite(pinoLed3, HIGH);	//SE SORT=4
    digitalWrite(pinoLed4, HIGH);
    digitalWrite(pinoLed6, HIGH);
  }
  
  if(numeroSorteado==5) {
    digitalWrite(pinoLed1, HIGH);
    digitalWrite(pinoLed3, HIGH);
    digitalWrite(pinoLed6, HIGH); 	//SE SORT=5
    digitalWrite(pinoLed7, HIGH);
    digitalWrite(pinoLed4, HIGH); 
  }
  
  if(numeroSorteado==6) {
    digitalWrite(pinoLed1, HIGH);
    digitalWrite(pinoLed2, HIGH);
    digitalWrite(pinoLed3, HIGH);	//SE SORT=6
    digitalWrite(pinoLed5, HIGH);
    digitalWrite(pinoLed6, HIGH);
    digitalWrite(pinoLed4, HIGH);
  }

  delay(2000);

  // RESET
  digitalWrite(pinoLed1, LOW);
  digitalWrite(pinoLed2, LOW);
  digitalWrite(pinoLed3, LOW);
  digitalWrite(pinoLed4, LOW);
  digitalWrite(pinoLed5, LOW);
  digitalWrite(pinoLed6, LOW);
  digitalWrite(pinoLed7, LOW);
}

``` 

