# Código atividade 1:

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
  digitalWrite(5, HIGH);
  digitalWrite(10, HIGH);
  delay(500); // Wait for 500 millisecond(s)
  digitalWrite(10, LOW);
  delay(1000); // Wait for 1000 millisecond(s)
  digitalWrite(10, HIGH);
  delay(5000); // Wait for 5000 millisecond(s)
  digitalWrite(5, LOW);
  digitalWrite(10, LOW);
  
  digitalWrite(4, HIGH);
  delay(2000); // Wait for 2000 millisecond(s)
  digitalWrite(4, LOW);
  
  digitalWrite(3, HIGH);
  digitalWrite(9, HIGH);
  delay(6000); // Wait for 6000 millisecond(s)
  digitalWrite(3, LOW);
  digitalWrite(9, LOW);
}
```

# Imagem do projeto:

<img width="1920" height="848" alt="image" src="https://github.com/user-attachments/assets/9f5d0a85-5019-4bdd-846e-6b74e0ffc905" />
