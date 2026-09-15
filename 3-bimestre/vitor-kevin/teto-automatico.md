<h1>Teto automático</h1>

<p>Imagem:</p>
<img width="1145" height="522" alt="image" src="https://github.com/user-attachments/assets/5b6ad6e8-7547-4d50-86dd-40dd044c60bb" />

---

<p>Código:</p>

```
#include <Servo.h>

#define PINO_LUZ A2
#define PINO_TEMPERATURA A1
#define PINO_MOTOR 3
#define PINO_LED_ABERTO 6
#define PINO_LED_FECHADO 5

const float LIMITE_TEMPERATURA = 28.0;
const int LIMITE_LUMINOSIDADE = 700;

Servo motorTelhado;

float lerTemperatura() {
  int leitura = analogRead(PINO_TEMPERATURA);
  float tensao = leitura * 5.0 / 1023.0;
  float temperatura = (tensao - 0.5) * 100.0;

  return temperatura;
}

bool deveFechar(int luminosidade, float temperatura) {
  if (luminosidade < LIMITE_LUMINOSIDADE) {
    return true;
  }

  if (temperatura > LIMITE_TEMPERATURA) {
    return true;
  }

  return false;
}

void atualizarTelhado(bool fechado) {
  if (fechado) {
    motorTelhado.write(0);

    digitalWrite(PINO_LED_ABERTO, LOW);
    digitalWrite(PINO_LED_FECHADO, HIGH);
  } 
  else {
    motorTelhado.write(90);

    digitalWrite(PINO_LED_ABERTO, HIGH);
    digitalWrite(PINO_LED_FECHADO, LOW);
  }
}

void setup() {
  pinMode(PINO_LED_ABERTO, OUTPUT);
  pinMode(PINO_LED_FECHADO, OUTPUT);

  motorTelhado.attach(PINO_MOTOR);

  atualizarTelhado(true);

  Serial.begin(9600);
}

void loop() {
  int luminosidade = analogRead(PINO_LUZ);
  float temperatura = lerTemperatura();

  bool fechar = deveFechar(luminosidade, temperatura);

  atualizarTelhado(fechar);

  Serial.print("Luz: ");
  Serial.print(luminosidade);

  Serial.print(" | Temperatura: ");
  Serial.print(temperatura);
  Serial.println(" C");

  delay(500);
}
```
