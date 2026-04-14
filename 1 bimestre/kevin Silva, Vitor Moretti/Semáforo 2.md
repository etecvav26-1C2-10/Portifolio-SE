# Código atividade 2

```bash
// C++ code
//
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
  
}

void loop()
{
  //verde, vermelho, vermelho 
  digitalWrite(5, HIGH);
  digitalWrite(10, HIGH);
  digitalWrite(6, HIGH);
  delay(500); 
  
  //piscada
  digitalWrite(10, LOW);
  delay(1000); 
  digitalWrite(10, HIGH);
  
  
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
```
<img width="1920" height="848" alt="image" src="https://github.com/user-attachments/assets/762d74b3-7e80-4e87-a321-583805f39c36" />

