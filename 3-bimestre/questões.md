# Questões — Sistemas Embarcados e IoT

## Questão 1 — O LED acendeu. Está tudo certo?

Não necessariamente. O fato de o LED ter acendido significa apenas que houve passagem de corrente pelo circuito, mas isso não garante que a ligação esteja correta ou segura.

É importante conhecer **tensão, corrente e resistência**, porque um LED normalmente precisa de uma corrente limitada. Se ele for ligado diretamente a um pino do microcontrolador sem um resistor adequado, pode passar uma corrente maior do que a recomendada. Isso pode diminuir a vida útil do LED e até danificar o pino do microcontrolador.

* **Tensão:** é a diferença de potencial que faz a corrente circular.
* **Corrente:** é o fluxo de cargas elétricas pelo circuito.
* **Resistência:** limita a corrente que passa pelo circuito.

Por isso, mesmo que o circuito esteja funcionando aparentemente bem, é necessário verificar se os valores elétricos estão dentro dos limites dos componentes.

**Conclusão:** não podemos dizer que a ligação está correta apenas porque o LED acendeu. É preciso verificar tensão, corrente, resistência e os limites dos componentes.

---

## Questão 2 — Escolhendo sensores

### 1. Qual informação precisa ser detectada?

É necessário detectar se existe ou não uma pessoa na sala. Também poderia ser interessante detectar há quanto tempo a sala está sem pessoas.

### 2. Que tipo de sensor poderia ser utilizado?

Uma opção seria utilizar um **sensor de presença PIR (infravermelho passivo)**. Ele consegue detectar movimento de pessoas no ambiente.

Outra possibilidade seria utilizar sensores de presença mais sofisticados, dependendo das necessidades do projeto.

### 3. Qual seria a função do microcontrolador?

O microcontrolador receberia as informações do sensor, analisaria esses dados e decidiria quando as luzes deveriam ser ligadas ou desligadas.

### 4. Qual seria o atuador?

O atuador poderia ser um **relé**, responsável por controlar o circuito das lâmpadas. Em um sistema de baixa tensão, também poderia ser utilizado um LED como representação da iluminação.

### 5. Que decisões o programa precisaria tomar?

Por exemplo:

* Se houver alguém na sala → manter as luzes ligadas.
* Se não houver ninguém durante determinado período → desligar as luzes.
* Se uma pessoa entrar novamente → ligar as luzes.
* Poderia existir também um modo manual para permitir que alguém controle a iluminação.

### Representação

```text
SENSOR DE PRESENÇA
        ↓
   MICROCONTROLADOR
        ↓
     RELÉ / LED
        ↓
      LUZES
```

Ou, de forma mais resumida:

```text
ENTRADA → PROCESSAMENTO → SAÍDA
Sensor       ESP32/Arduino     Relé → Lâmpada
de presença
```

---

## Questão 3 — Sensor ou atuador?

| Componente             | Classificação | Função                                   |
| ---------------------- | ------------- | ---------------------------------------- |
| Sensor de temperatura  | Entrada       | Mede a temperatura do ambiente           |
| Sensor de luminosidade | Entrada       | Mede a quantidade de luz                 |
| Botão                  | Entrada       | Permite que o usuário envie um comando   |
| Motor                  | Saída         | Realiza um movimento                     |
| LED                    | Saída         | Emite luz para indicar alguma informação |
| Buzzer                 | Saída         | Emite um sinal sonoro                    |
| ESP32                  | Processamento | Recebe informações e executa o programa  |

Um projeto pode precisar de vários sensores porque diferentes sensores fornecem informações diferentes sobre o ambiente. Da mesma forma, pode precisar de vários atuadores porque diferentes ações podem ser necessárias.

### Exemplo

Imagine um sistema automático para uma estufa:

```text
Sensor de temperatura ──┐
                        │
Sensor de luminosidade ─┼──→ ESP32 ──→ Ventilador
                        │           ├─→ LED
Sensor de umidade ──────┘           └─→ Bomba
```

Nesse exemplo, o ESP32 recebe informações de vários sensores e pode controlar vários atuadores de acordo com essas informações.

Por exemplo:

* Se a temperatura estiver muito alta, o ventilador pode ser ligado.
* Se o ambiente estiver muito escuro, uma iluminação pode ser acionada.
* Se o solo estiver seco, a bomba pode ser ativada.

---

## Questão 4 — Automatizar tudo é sempre melhor?

Não. A informação de que o solo está seco não deve ser necessariamente suficiente para ligar a bomba imediatamente.

O sistema precisa considerar outras condições para evitar erros ou danos.

Por exemplo:

* **Defeito no sensor:** o sensor pode fornecer uma informação incorreta.
* **Duração da irrigação:** a bomba não deve funcionar indefinidamente.
* **Disponibilidade de água:** é necessário verificar se existe água suficiente.
* **Horário:** pode ser melhor irrigar em determinados horários.
* **Acionamento manual:** o usuário pode precisar controlar a bomba manualmente.
* **Falha na comunicação:** se o sistema depender de comunicação com outro dispositivo, deve saber o que fazer quando essa comunicação falhar.
* **Limite de umidade:** a bomba pode funcionar por determinado tempo e depois verificar novamente a umidade.

Uma lógica mais segura poderia ser:

```text
Solo está seco?
       ↓
      SIM
       ↓
Sensor está funcionando?
       ↓
      SIM
       ↓
Há água disponível?
       ↓
      SIM
       ↓
Está dentro do horário permitido?
       ↓
      SIM
       ↓
Ligar bomba por determinado tempo
       ↓
Desligar bomba
       ↓
Verificar novamente
```

Portanto, um sistema automatizado precisa prever situações inesperadas e condições de segurança. Automatizar não significa simplesmente fazer uma ação sempre que uma condição acontecer. É necessário analisar diferentes informações e definir o que deve acontecer em situações normais e também em situações de erro.

---

## Questão 5 — Quando um projeto se torna IoT?

Os dois sistemas possuem sensores e microcontroladores, mas não necessariamente os dois são considerados IoT.

### Sistema A

```text
Sensor de temperatura
        ↓
      Arduino
        ↓
        LED
```

Esse sistema pode ser considerado um **sistema eletrônico automatizado**. O Arduino recebe a informação do sensor, processa os dados e controla o LED, mas não existe necessariamente uma comunicação com a Internet.

### Sistema B

```text
Sensor de temperatura
        ↓
       ESP32
        ↓
       Wi-Fi
        ↓
      Internet
        ↓
    Aplicativo
```

O Sistema B se aproxima claramente do conceito de **Internet das Coisas (IoT)** porque o dispositivo está conectado a uma rede e consegue enviar ou receber informações por meio da Internet.

Por exemplo, o ESP32 poderia medir a temperatura de uma sala e enviar essa informação para um aplicativo. O usuário poderia consultar a temperatura mesmo estando longe do dispositivo.

### Diferença principal

Um sistema eletrônico ou automatizado pode funcionar localmente, sem precisar estar conectado à Internet.

Um sistema IoT normalmente envolve:

* dispositivos físicos com sensores e/ou atuadores;
* processamento por um microcontrolador ou outro dispositivo;
* comunicação em rede;
* troca de dados;
* possibilidade de monitoramento ou controle remoto.

**Portanto:**

* **Sistema A:** eletrônico/automatizado, mas não necessariamente IoT.
* **Sistema B:** pode ser considerado um sistema de Internet das Coisas, pois utiliza conectividade para trocar informações com outros sistemas através da rede.

---

## Conclusão geral

A principal diferença não é simplesmente usar um ESP32 em vez de um Arduino. O que aproxima um projeto de IoT é a **conectividade e a troca de dados entre o dispositivo e outros sistemas por uma rede**, geralmente permitindo monitoramento, controle ou integração remota.
