# Projeto Semaforo


## Parte 1: Montagem Física do Semáforo

### Imagens da Montagem

<div align="center">
<sub>Figura 1 — Semaforo Lado <a href="#c6"></a></sub> </br>
<img src="Assets\Semaforo Lado.jpg"><br>
</div><br>

<div align="center">
<sub>Figura 2 — Semaforo Topo <a href="#c6"></a></sub> </br>
<img src="Assets\Semaforo Topo.jpg"><br>
</div><br>

O sistema de Semáforo opera com um botão que pode ser ativado por um pedestre para parar os carros, um buzzer e três LEDs. O botão é monitorado continuamente para verificar seu estado e, ao ser pressionado, ativa o sistema. Nesse momento, o buzzer emite sons e as LEDs ativam de acordo com o ciclo do semáforo: do verde para o amarelo, do amarelo para o vermelho, e depois de volta ao amarelo e em seguinte o verde, completando o processo. Durante a mudança das LEDs, o buzzer emite sons para sinalizar cada etapa de transição.

### Video do Funcionamento
https://github.com/user-attachments/assets/5d1e3c31-689a-4b35-85cb-791781f4b97e


## Parte 2: Programação e Lógica do Semáforo

### Tabela de Itens
- 3 LEDs (Verde, Amarelo, Vermelho)
- 1 Buzzer
- 1 Botão
- 1 Resistor 10k (Botão)
- 3 Resistores 1k (LEDs)
- 8 Jumpers (Macho Macho)
- 6 Jumpers (Macho Femea)
- 1 Protoboard

### Codigo do Semaforo
```
// Definindo os pins das LEDs e do botao
int Vermelho = 10;
int Amarelo = 9;
int Verde = 8;
int Botao = 7; 
int Buzzer = 6; 

void setup() {
  
  // Definindo os pins das LEDs como output
  pinMode(Vermelho, OUTPUT);
  pinMode(Amarelo, OUTPUT);
  pinMode(Verde, OUTPUT);
  
  // Definindo o pin do botão como input
  pinMode(Botao, INPUT);

  // Definindo o pin do buzzer como output
  pinMode(Buzzer, OUTPUT);

  digitalWrite(Verde, HIGH);
}

void loop() {
  // Verificando se o botao foi pressionado
  if (digitalRead(Botao) == HIGH) {
    // Se o botao foi pressionado, ativa o loop
    

    // Ciclo do semaforo

    // Ativa o verde e um delay inicial de 1 segundo
    digitalWrite(Amarelo, LOW);
    digitalWrite(Vermelho, LOW);
    digitalWrite(Verde, HIGH);
    delay(1000);
    
    // Ativa o Amarelo com delay de 2 segundos
    digitalWrite(Verde, LOW);
    digitalWrite(Buzzer, HIGH);
    digitalWrite(Amarelo, HIGH);
    delay(500);
    digitalWrite(Buzzer, LOW);
    delay(1500);

    // Ativa o Vermelho com delay de 6 segundos
    digitalWrite(Vermelho, HIGH);
    digitalWrite(Amarelo, LOW);
    digitalWrite(Buzzer, HIGH);
    delay(2000);
    digitalWrite(Buzzer, LOW);
    delay(4000);

    // Ativa o Amarelo com delay de 2 segundos
    digitalWrite(Vermelho, LOW);
    digitalWrite(Buzzer, HIGH);
    digitalWrite(Amarelo, HIGH);
    delay(500);
    digitalWrite(Buzzer, LOW);
    delay(1500);

    // Ativa o Verde com delay de 4 segundos
    digitalWrite(Amarelo, LOW);
    digitalWrite(Verde, HIGH);
    digitalWrite(Buzzer, HIGH);
    delay(500);
    digitalWrite(Buzzer, LOW);
    delay(3500);

  }
  // Caso o botão nao esteja pressionado, o sistema fica esperando
}
```


## Parte 3: Avaliação de Pares


### Avaliador: Felipe Freire Machado Simão

| Critério                                                                                                 | Contempla (Pontos) | Contempla Parcialmente (Pontos) | Não Contempla (Pontos) | Observações do Avaliador |
|---------------------------------------------------------------------------------------------------------|--------------------|----------------------------------|--------------------------|---------------------------|
| Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores                | Até 3              | Até 1,5                            | 0                        |A montagem esta correta pela quantidade de itens sendo utilizados porem os cabos conectados aos LEDs são da mesma cor.                           |
| Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo                  | Até 3              | Até 1,5                          | 0                        |Tempo esta correto porem o loop inicia no verde para o funcionamento correto desse semaforo e o sistema apenas inicia com o botão.                           |
| Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) | Até 3              | Até 1,5                          | 0                        | Codigo implementado corretamente com as fases, variaveis e comentarios.                           |
| Extra: Implementou um componente de liga/desliga no semáforo e/ou usou ponteiros no código | Até 1              |  Até 0,5                         | 0                        | Implementou um botão e buzzer no sistema que quando o botão é ativado o sistema inicia representando um semafaro de pasagem de pedestres.                      |
|  |                                                             |   | 9.2 |**Pontuação Total**|

