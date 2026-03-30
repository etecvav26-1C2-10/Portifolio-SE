## Kevin Silva Fernandes, Vitor Moretti
## Turma: 1ºC2
## Etec Vasco Antonio Venchiarutti

 Vitor Moretti - Exercicio 1 - Pergunta concenitual
-Explique com suas palavras o que é Internet das Coisas (IoT) e cite um exemplo do cotidiano.

R:A Internet das Coisas (IoT) é um conceito da área de Tecnologia da Informação que se refere à conexão de objetos do dia a dia à internet, permitindo que eles coletem e troquem dados automaticamente. Esses objetos podem ser desde eletrodomésticos até carros e dispositivos vestíveis, todos equipados com sensores e softwares. A ideia principal é tornar esses itens “inteligentes”, capazes de tomar decisões ou enviar informações sem intervenção humana constante. Isso facilita a automação de tarefas, melhora a eficiência e pode trazer mais conforto e segurança para as pessoas.Um exemplo comum no cotidiano é uma lâmpada inteligente, que pode ser controlada pelo celular: você pode ligar ou desligar a luz, ajustar a intensidade ou até programar horários ciclicos, tudo à distância ou com intervenção minima.

Kevin Silva Fernandes - exercicios 2 - Pergunta de aplicação
-Descreva como um sistema embarcado podweria ser usado para automatizar a iluminação de uma casa

R:Um sistema embarcado pode ser usado para automatizar a iluminação de uma casa ao controlar as lâmpadas de forma inteligente, sem depender apenas da ação manual das pessoas. Esse sistema é composto por um microcontrolador, sensores (como de presença ou luminosidade) e atuadores que ligam e desligam as luzes.Por exemplo, sensores de presença podem detectar quando alguém entra em um cômodo e acender automaticamente a luz, desligando após um tempo sem movimento. Já sensores de luz podem identificar se o ambiente está escuro e ajustar a iluminação conforme necessário.
Além disso, o sistema pode ser programado para seguir horários específicos, como acender luzes ao anoitecer e apagar ao amanhecer. Também é possível integrar tudo com um aplicativo no celular, permitindo controlar as luzes à distância.Dessa forma, o uso de um sistema embarcado torna a casa mais prática, econômica e eficiente no uso de energia.

Vitor Moretti - Exercicio 3 - Pergunta de Investigação
-Utilize o simulador Wolki ou Tinkercad Para montar um circuito com LED. Teste diferentes tipo de delay e registre o comportamento observado.

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
.
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
.
Com 500 ms já é mais estável e notável, cujo código é: 

 digitalWrite(3, HIGH);
  delay(500);
 .

Kevin Silva Fernandes - Exercício 4 - Pergunta de reflexão
-Quais são as vantagens e desvantagens do uso de hardware open source em projetos iot?

R:O uso de hardware open source em projetos de IoT tem várias vantagens, principalmente para quem está começando ou quer economizar. Em geral, esses dispositivos são mais baratos e fáceis de encontrar, além de terem muita documentação disponível na internet. Outra vantagem é a liberdade de modificar o projeto do jeito que quiser, adaptando às suas necessidades. Também existe uma comunidade grande que ajuda bastante, com fóruns, vídeos e exemplos práticos.Por outro lado, nem tudo é perfeito. Como não há sempre um suporte oficial, às vezes pode ser difícil resolver problemas mais específicos. A segurança também pode ser um ponto fraco se o projeto não for bem configurado, já que tudo é mais aberto. Além disso, alguns componentes podem ter qualidade variável ou não seguir um padrão tão rígido, o que pode gerar dificuldades na integração.No fim das contas, o hardware open source é uma ótima opção, mas é importante ter um pouco de cuidado e planejamento para evitar dores de cabeça no projeto.

Vitor Moretti - exercicio 5 - Pergunta conceitual
-Qual a função de um microcontrolador em um sistema embarcado? 

R:O microcontrolador é basicamente o “cérebro” de um sistema embarcado. Ele é responsável por receber informações dos sensores, processar esses dados e tomar decisões com base no que foi programado. Ou seja, é ele quem controla todo o funcionamento do sistema. Por exemplo, em um sistema de iluminação automática, o microcontrolador recebe o sinal de um sensor de presença. Se detectar alguém no ambiente, ele processa essa informação e envia um comando para acender a luz. Quando não há mais movimento, ele pode desligar depois de um tempo. Além disso, o microcontrolador também pode controlar o tempo das ações, armazenar pequenas quantidades de dados e se comunicar com outros dispositivos. Sem ele, o sistema embarcado não teria “inteligência” para funcionar de forma automática.

Kevin Silva Fernandes - Exercício 6 - Pergunta de aplicação
-Proponha um projeto simples utilizando sensores e atuadores para resolver o problema real.

R: projeto que usa a detecção da luz solar em um determinado horario para irrigar as plantas: O sistema pode usar um microcontrolador, um sensor de luminosidade (LDR) para detectar a intensidade da luz solar e um módulo de relógio (RTC) para verificar o horário. Como atuador, seria utilizada uma pequena bomba de água ou uma válvula elétrica para liberar a irrigação.Na prática, o sistema funcionaria assim: o sensor de luz identifica se há presença de luz solar e mede sua intensidade. Ao mesmo tempo, o relógio verifica se está dentro de um horário programado, como início da manhã ou final da tarde. Se as duas condições forem atendidas (luz adequada e horário correto), o microcontrolador aciona a bomba de água para irrigar as plantas por um tempo determinado.Esse tipo de projeto é simples, econômico e ajuda a economizar água, além de cuidar melhor das plantas sem necessidade de intervenção constante.

Vitor Moretti - exercicio 7 - Pergunta de investigação
-No simulador, adicione um botão ao circuito do LED. Programe para que o LED acenda apenas quando o botão for pressionado. Descreva o Funcionamento.

R: O LED está conectado a um pino de saída do Arduino, enquanto o botão está ligado a um pino de entrada. Quando o circuito está em repouso (ou seja, quando o botão não está sendo pressionado), o Arduino lê um valor baixo (LOW) no pino do botão. Com isso, ele mantém o LED apagado.Quando o botão é pressionado, ele fecha o circuito e permite que a corrente elétrica chegue ao pino de entrada do Arduino, fazendo com que ele leia um valor alto (HIGH). Ao identificar esse sinal, o Arduino envia energia para o pino onde o LED está conectado, fazendo com que ele acenda. Assim que o botão é solto, o circuito se abre novamente, o sinal volta para LOW e o Arduino desliga o LED.

Kevin silva - Exercício 8 - Pergunta de reflexão
-Como o movimento maker contribui para o aprendizado em tecnologia?

R: Ele cria espaço para que o estudante possa ter experiencia na forma prática do objeto de estudo, aprendendo com seus erros e acertos bem como a compartilha-los, criando senso critico e se adaptando ao funcionamento do sistema, o preparando mais adequadamente ao mercado de trabalho. Esse formato pode incluir ambitos como a ciencia, arte, engenharia, matematica e tecnologia, como no caso do Tinkercad ou outros simuladores, que possibilita testar os conceitos mais básicos de um sistema embarcado (arduinos e Raspberry Pi) e dá espaço para aprofundamentos, também instigando a curiosidade mesmo daquele que não tem um objetivo profissional.

Vitor Moretti - exercicio 9 - Pergunta de aplicação 
-Explique como sensores e atuadores trabalham juntos em um sistema de irrigação automatizado.

R: Em um sistema de irrigação automatizado, sensores, controladores e atuadores trabalham em conjunto para tomar decisões e agir sem intervenção humana. A ideia é de que os sensores detectem informações como humidade do solo, temperatura externa, preciptação e intensidade da incidência da luz solar no ambiente, enviando os dados aos controladores que, ao analizarem, decidem se os atuadores executarão suas ações com base nessas informações, como, por exemplo, se a humidade do solo estiver abaixo de 30%, ligar os irrigadores. Com isso é possível economizar agua e mão de obra, ainda sendo capaz de aumentar a eficiencia.

Kevin Fernandes - exercício 10 - pergunta de investigação
-Explore um projeto pronto no Wokwi ou Tinkercad. Modifique algum parâmetro (tempo, sensor, etc.) e descreva oq mudou.

R: No projeto original, o LED piscava com um intervalo de 1 segundo (1000 ms), então eu modifiquei esse parâmetro no código, alterando o tempo para 300 ms. Depois da alteração, o LED passou a piscar muito mais rápido, porque antes dava pra perceber claramente o tempo ligado e desligado, mas depois da mudança ele ficou quase contínuo, piscando em alta velocidade. Essa modificação mostrou como o tempo no código influencia diretamente o comportamento do circuito, já que pequenas mudanças nos valores podem alterar bastante o resultado final do projeto.
