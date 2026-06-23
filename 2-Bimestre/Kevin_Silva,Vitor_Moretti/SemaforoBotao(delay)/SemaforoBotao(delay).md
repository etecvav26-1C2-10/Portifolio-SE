# Vitor Moretti e Kevin Silva- 1ºc2
<p> Semáforo com botão e usando delay();</p>

<p>Imagem</p>
<img width="1920" height="848" alt="Copy of Tremendous Blad-Hillar" src="https://github.com/user-attachments/assets/86311d12-8c4c-4be4-b177-b20f2c05e897" />

<p>Código: </p>

```

void setup()
{
  pinMode(3, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(5, OUTPUT);
  pinMode(6, OUTPUT);
  pinMode(7, OUTPUT);
  pinMode(8, OUTPUT);
  pinMode(9, OUTPUT);
  pinMode(10, OUTPUT);
  
  pinMode (11, INPUT);
}

void loop()
{
  if(digitalRead(11)== LOW)
  {
    //verde, vermelho, vermelho 
    digitalWrite(5, HIGH);
    digitalWrite(10, HIGH);
    digitalWrite(6, HIGH);
    delay(5000);
	digitalWrite(5, LOW);

    //Amarelo, amaraelo, vermelho 
    digitalWrite(4, HIGH);
    digitalWrite(6, LOW);
    digitalWrite(7, HIGH);
    delay(2000); //
    digitalWrite(4, LOW);
    digitalWrite(7, LOW);

    //vermelho, verde, vermelho
    digitalWrite(3, HIGH);
    digitalWrite(8, HIGH);
     delay(6000); 
    digitalWrite(8, LOW);
    digitalWrite(10, LOW);

    //vermelho,vermelho, verde

    digitalWrite(9, HIGH);
    digitalWrite(6, HIGH);
    delay(4000);
    digitalWrite(9, LOW);
    digitalWrite(3, LOW); 
  }
  else {
    digitalWrite(6, HIGH);
    digitalWrite(3, HIGH);
    digitalWrite(9, HIGH);
	delay (500);
	
	
	digitalWrite(5, HIGH);
    digitalWrite(10, HIGH);
    digitalWrite(6, HIGH);
    delay(5000);
	
	

    //Amarelo, amaraelo, vermelho 
    digitalWrite(4, HIGH);
    digitalWrite(6, LOW);
    digitalWrite(7, HIGH);
    delay(2000); //
    digitalWrite(4, LOW);
    digitalWrite(7, LOW);

    //vermelho, verde, vermelho
    digitalWrite(3, HIGH);
    digitalWrite(8, HIGH);
     delay(6000); 
    digitalWrite(8, LOW);
    digitalWrite(10, LOW);

    //vermelho,vermelho, verde

    digitalWrite(9, HIGH);
    digitalWrite(6, HIGH);
    delay(4000);
    digitalWrite(9, LOW);
    digitalWrite(3, LOW); 

  }
}
```
