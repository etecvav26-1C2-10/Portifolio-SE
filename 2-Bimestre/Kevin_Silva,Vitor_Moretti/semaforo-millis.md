# VITOR MORETTI - KEVIN SILVA 1ºc2
<p>Semáforo com botão e só usando millis durante o ciclo dos carros</p>

<p>Imagem:</p>
<img width="1511" height="568" alt="Copy of Copy of Tremendous Blad-Hillar" src="https://github.com/user-attachments/assets/1f166894-47b8-4108-94f8-365b6ad93ca6" />

<p>Código:</p>

```
// C++ code
//

// DEF
int botaoP = 0;
int posicao = 0;
unsigned long tempo = 0;
#define Tverde 5000
int tama = 2000;

void setup()
{
  //OUT
  pinMode(3, OUTPUT);	// Vermelho carros 1
  pinMode(4, OUTPUT);	// amarelo carros 1
  pinMode(5, OUTPUT);	// Verde carros 1
  pinMode(6, OUTPUT);	// Vermelho carros 2
  pinMode(7, OUTPUT);	// amarelo carros 2
  pinMode(8, OUTPUT);	// verde carros 2
  pinMode(9, OUTPUT);	// verde pedestre
  pinMode(10, OUTPUT);	// vermehlo pedestre
  //IN
  pinMode (11, INPUT);	//
  
  //RE-DEF
  tempo = millis();
  posicao = 1;
  digitalWrite (3, HIGH);
  digitalWrite (6, HIGH);
  digitalWrite (10, HIGH);
}

void loop()
{
  if(digitalRead(11) == HIGH){
  	botaoP = 1;
  }
  //POSIÇÃO 1//
  if(posicao == 1){
   	
    digitalWrite (3, LOW);
    digitalWrite (5, HIGH);
    digitalWrite (6, HIGH);
    
    
   
    if(millis() - tempo >= Tverde){
      	digitalWrite (5, LOW);
      	digitalWrite (6, LOW);
      	digitalWrite (4, HIGH);
      	digitalWrite (7, HIGH);
      
      	if(botaoP == 1){	
    	pedestre();
      	return;
    	}
          
      	posicao = 2;
      	tempo = millis();
    }
  }
  //POSIÇÃO 2//
  if(posicao == 2){
    if(millis() - tempo >= tama){
      digitalWrite (4, LOW);
      digitalWrite (3, HIGH);
      
      if(botaoP == 1){	
      	pedestre();
       	return; 
       }
      
      digitalWrite(8, HIGH);
      digitalWrite(6, LOW);
      digitalWrite(7, LOW);
      posicao = 3;
      tempo = millis();
    }
  }
  //POSIÇÃO 3//
  if(posicao == 3)
{
    digitalWrite(8, HIGH);
    digitalWrite(4, LOW);
    digitalWrite(3, HIGH);

    if(millis() - tempo >= 5000)
    {
        
        botaoP = 0;
        pedestre();
        tempo = millis();
    }
  }
}

void pedestre()
{
  	digitalWrite (9, HIGH);
  	digitalWrite (3, HIGH);
  	digitalWrite (6, HIGH);
  
  	digitalWrite (8, LOW);
  	digitalWrite (10, LOW);
  	digitalWrite (5, LOW);
  
  	digitalWrite (4, LOW);
  	digitalWrite (7, LOW);
  
  	delay (2000);
  
  	digitalWrite (9, LOW);
  	digitalWrite (10, HIGH);
  
  	botaoP = 0; 
  	posicao=1;
  	tempo = millis();
}
```
