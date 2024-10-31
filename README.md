# Ponderada Sinaleiro
 ```cpp

codigo
```

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

void setup() {
  // Configurando as portas dos LEDs como saídas
  pinMode(ledVermelho, OUTPUT);
  pinMode(ledAmarelo, OUTPUT);
  pinMode(ledVerde, OUTPUT);
}

void loop() {
  // Fase Vermelha - 6 segundos
  digitalWrite(ledVermelho, HIGH);
  digitalWrite(ledAmarelo, LOW);
  digitalWrite(ledVerde, LOW);
  delay(6000); // Espera 6 segundos

  // Fase Amarela - 2 segundos
  digitalWrite(ledVermelho, LOW);
  digitalWrite(ledAmarelo, HIGH);
  digitalWrite(ledVerde, LOW);
  delay(2000); // Espera 2 segundos

  // Fase Verde - 2 segundos
  digitalWrite(ledVermelho, LOW);
  digitalWrite(ledAmarelo, LOW);
  digitalWrite(ledVerde, HIGH);
  delay(2000); // Espera 2 segundos

  // Tempo adicional no Verde - +2 segundos
  delay(2000); // Espera mais 2 segundos

  // Fase Amarela - 2 segundos antes de retornar ao vermelho
  digitalWrite(ledVermelho, LOW);
  digitalWrite(ledAmarelo, HIGH);
  digitalWrite(ledVerde, LOW);
  delay(2000); // Espera 2 segundos
}

```

# Parte 4 - Vídeo de demonstração

[Assista ao vídeo](./assets/ponderada_semaforo.mp4)


# Parte 5: Avaliação de Pares 

#### Avaliador: Ricardo Planas

|Critério|	Contempla (Pontos)|	Contempla Parcialmente (Pontos)	|Não Contempla (Pontos)	|Observações do Avaliador|
|-|-|-|-|-|
|Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores	|Até 3	|Até 1,5	|0 | |	
|Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo	|Até 3	|Até 1,5	|0 | |	
|Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) |	Até 3|	Até 1,5 |	0 | |	
|Ir além: Implementou um componente de extra, fez com millis() ao invés do delay() e/ou usou ponteiros no código |	Até 1 |	Até 0,5 |	0 | |	

### Tabela de Avaliação entre Pares

#### Avaliador: Nome do Avaliador

|Critério|	Contempla (Pontos)|	Contempla Parcialmente (Pontos)	|Não Contempla (Pontos)	|Observações do Avaliador|
|-|-|-|-|-|
|Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores	|Até 3	|Até 1,5	|0 | |	
|Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo	|Até 3	|Até 1,5	|0 | |	
|Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) |	Até 3|	Até 1,5 |	0 | |	
|Ir além: Implementou um componente de extra, fez com millis() ao invés do delay() e/ou usou ponteiros no código |	Até 1 |	Até 0,5 |	0 | |
