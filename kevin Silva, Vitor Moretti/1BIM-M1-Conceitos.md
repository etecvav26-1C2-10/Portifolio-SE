Kevin Silva Fernandes, Vitor Moretti
Turma: 1ºC2
Etec Vasco Antonio Venchiarutti

Vitor Moretti - Exercicio 1 
Explique com suas palavras o que é Internet das Coisas (IoT) e cite um exemplo do cotidiano.

R:A Internet das Coisas (IoT) é um conceito da área de Tecnologia da Informação que se refere à conexão de objetos do dia a dia à internet, permitindo que eles coletem e troquem dados automaticamente. Esses objetos podem ser desde eletrodomésticos até carros e dispositivos vestíveis, todos equipados com sensores e softwares. A ideia principal é tornar esses itens “inteligentes”, capazes de tomar decisões ou enviar informações sem intervenção humana constante. Isso facilita a automação de tarefas, melhora a eficiência e pode trazer mais conforto e segurança para as pessoas.Um exemplo comum no cotidiano é uma lâmpada inteligente, que pode ser controlada pelo celular: você pode ligar ou desligar a luz, ajustar a intensidade ou até programar horários ciclicos, tudo à distância ou com intervenção minima.

Kevin Silva Fernandes - exercicios 2 - Pergunta de aplicação
Descreva como um sistema embarcado podweria ser usado para automatizar a iluminação de uma casa

R:Um sistema embarcado pode ser usado para automatizar a iluminação de uma casa ao controlar as lâmpadas de forma inteligente, sem depender apenas da ação manual das pessoas. Esse sistema é composto por um microcontrolador, sensores (como de presença ou luminosidade) e atuadores que ligam e desligam as luzes.Por exemplo, sensores de presença podem detectar quando alguém entra em um cômodo e acender automaticamente a luz, desligando após um tempo sem movimento. Já sensores de luz podem identificar se o ambiente está escuro e ajustar a iluminação conforme necessário.
Além disso, o sistema pode ser programado para seguir horários específicos, como acender luzes ao anoitecer e apagar ao amanhecer. Também é possível integrar tudo com um aplicativo no celular, permitindo controlar as luzes à distância.Dessa forma, o uso de um sistema embarcado torna a casa mais prática, econômica e eficiente no uso de energia.

Vitor Moretti - Exercicio 3
Utilize o simulador Wolki ou Tinkercad Para montar um circuito com LED. Teste diferentes tipo de delay e registre o comportamento observado.

R: Com delay de 100 ms (0,1 segundos) o LED tem ação quase imperceptivel: 

void setup()
{
 pinMode(3, OUTPUT);
}
void loop()
{
 digitalWrite(3, HIGH);
  delay(100);
}

porém se continuo torna-se claro:

void setup()
{
 pinMode(3, OUTPUT);
}
void loop()
{
 digitalWrite(3, HIGH);
  delay(100);
   digitalWrite(3, LOW);
  delay(100);
   digitalWrite(3, HIGH);
  delay(100);
   digitalWrite(3, LOW);
  delay(100);
  
}

Com 500 ms já é mais estável e notável, cujo código é: 

 digitalWrite(3, HIGH);
  delay(500);


