# Ponderada Farol

*Ponderada Arduino - Semana 2 (Projeto Farol)*

Pedro El Haouli Faria
Turma: 12  

#

# Parte 1 - Montagem Física do Semáforo

[imagem](./imagem.jpg)

# Parte 2 - Relato

# Parte 3 - Código

 ```cpp
// Definindo as portas dos LEDs
const int ledVermelho = 13;
const int ledAmarelo = 12;
const int ledVerde = 11;

// Definindo as durações das fases em milissegundos
const unsigned long duracaoVermelho = 6000;
const unsigned long duracaoAmarelo = 2000;
const unsigned long duracaoVerde = 4000; // 2s + 2s extra no verde

// Variáveis para armazenar o tempo e o estado atual
unsigned long tempoAnterior = 0;
int estadoAtual = 0;

void setup() {
  // Configurando as portas dos LEDs como saídas
  pinMode(ledVermelho, OUTPUT);
  pinMode(ledAmarelo, OUTPUT);
  pinMode(ledVerde, OUTPUT);
}

void loop() {
  unsigned long tempoAtual = millis();

  // Verifica o tempo para mudar de estado
  if (estadoAtual == 0 && tempoAtual - tempoAnterior >= duracaoVermelho) {
    // Mudar para o estado Amarelo
    digitalWrite(ledVermelho, LOW);
    digitalWrite(ledAmarelo, HIGH);
    digitalWrite(ledVerde, LOW);
    estadoAtual = 1;
    tempoAnterior = tempoAtual;
  } 
  else if (estadoAtual == 1 && tempoAtual - tempoAnterior >= duracaoAmarelo) {
    // Mudar para o estado Verde
    digitalWrite(ledVermelho, LOW);
    digitalWrite(ledAmarelo, LOW);
    digitalWrite(ledVerde, HIGH);
    estadoAtual = 2;
    tempoAnterior = tempoAtual;
  } 
  else if (estadoAtual == 2 && tempoAtual - tempoAnterior >= duracaoVerde) {
    // Mudar para o estado Amarelo novamente antes de voltar ao Vermelho
    digitalWrite(ledVermelho, LOW);
    digitalWrite(ledAmarelo, HIGH);
    digitalWrite(ledVerde, LOW);
    estadoAtual = 3;
    tempoAnterior = tempoAtual;
  } 
  else if (estadoAtual == 3 && tempoAtual - tempoAnterior >= duracaoAmarelo) {
    // Voltar para o estado Vermelho
    digitalWrite(ledVermelho, HIGH);
    digitalWrite(ledAmarelo, LOW);
    digitalWrite(ledVerde, LOW);
    estadoAtual = 0;
    tempoAnterior = tempoAtual;
  }
}

```

# Parte 4 - Vídeo de demonstração

[Assista ao vídeo](./assets/ponderada_semaforo.mp4)


# Parte 5: Avaliação de Pares 

#### Avaliado por: Ricardo Planas

|Critério|	Contempla (Pontos)|	Contempla Parcialmente (Pontos)	|Não Contempla (Pontos)	|Observações do Avaliador|
|-|-|-|-|-|
|Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores	|Até 3	|Até 1,5	|0 | 3|	
|Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo	|Até 3	|Até 1,5	|0 | 3|	
|Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) |	Até 3|	Até 1,5 |	0 | 3|	
|Ir além: Implementou um componente de extra, fez com millis() ao invés do delay() e/ou usou ponteiros no código |	Até 1 |	Até 0,5 |	0 | 1|	

### Tabela de Avaliação entre Pares

#### Avaliador: Pedro El Haouli Faria
#### Avaliado: Ricardo Planas

|Critério|	Contempla (Pontos)|	Contempla Parcialmente (Pontos)	|Não Contempla (Pontos)	|Observações do Avaliador|
|-|-|-|-|-|
|Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores	|Até 3	|Até 1,5	|0 | 3|	
|Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo	|Até 3	|Até 1,5	|0 | 3|	
|Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) |	Até 3|	Até 1,5 |	0 | 3|	
|Ir além: Implementou um componente de extra, fez com millis() ao invés do delay() e/ou usou ponteiros no código |	Até 1 |	Até 0,5 |	0 | 1|

Ricardo usou as cores corretíssimas, o tempo ficou certinho, código ficou bem estruturado e ele foi além utilizando ponteiros no código.
