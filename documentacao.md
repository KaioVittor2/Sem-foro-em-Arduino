# Seção de Explicação Geral do Semáforo

O Semáforo criado tem a seguinte funcionalidade ao ligar:
- Acende o led vermelho por 6 segundos;
- Acende o led Amarelo por 2 segundos com:
    - 3 toques sonoros rápidos do buzzer em 0,6 s enquanto o led amarelo está acesso;
- Acende o led Verde por 2 segundos;
- Mantém o led Verde por mais 2 segundos acesso;
- Acende o led Amarelo por 2 segundos
- Reinicia o ciclo

# Seção de Vídeo Funcional

Aqui está o funcionamento do Semáforo com a emissão sonora do buzzer ao se acender a luz amarela.

Link: https://youtube.com/shorts/uqWOIkF8fnE?si=EUhgStETCuT4OTHA

# Seção de Código :)

```cpp
// Definição dos pinos dos LEDs e do buzzer
const int ledVermelho = 13;
const int ledAmarelo = 12;
const int ledVerde = 11;
const int buzzer = 10;

// Definição dos tempos em milissegundos
const int tempoVermelho = 6000; // 6 segundos
const int tempoAmarelo = 2000;  // 2 segundos
const int tempoVerde = 2000;    // 2 segundos

void setup() {
  // Configuração dos pinos como saídas
  pinMode(ledVermelho, OUTPUT);
  pinMode(ledAmarelo, OUTPUT);
  pinMode(ledVerde, OUTPUT);
  pinMode(buzzer, OUTPUT);
}

void loop() {
  // Acende o LED vermelho
  digitalWrite(ledVermelho, HIGH);
  delay(tempoVermelho);
  digitalWrite(ledVermelho, LOW);
  
    // Acende o LED amarelo
  digitalWrite(ledAmarelo, HIGH);

  // Ativa o buzzer 3 vezes 100 ms (0,1s)
  for (int i = 0; i < 3; i++) {
    digitalWrite(buzzer, HIGH);
    delay(100);           // Toca por 100 ms
    digitalWrite(buzzer, LOW); 
    delay(100);           // Pausa por 100 ms
  }
  delay(tempoAmarelo - 600); // Pausa pelo tempo Amarelo, descontado do tempo da função do buzzer.
  
  digitalWrite(ledAmarelo, LOW); // Apaga o LED amarelo

  // Acende o LED verde
  digitalWrite(ledVerde, HIGH);
  delay(tempoVerde);
  delay(tempoVerde); // Da o tempo de 2 segundos a mais para o pedestre passar
  digitalWrite(ledVerde, LOW);

  // Acende o LED amarelo e ativa o buzzer
  digitalWrite(ledAmarelo, HIGH);
  delay(tempoAmarelo); // Pausa pelo tempo Amarelo, descontado do tempo da função do buzzer.
  digitalWrite(ledAmarelo, LOW); // Apaga o LED amarelo e reinicia o ciclo
} 
```

# Seção de Avaliação em Pares

### Avaliador: Caio Santos

| Critério                                                                                                 | Contempla (Pontos) | Contempla Parcialmente (Pontos) | Não Contempla (Pontos) | Observações do Avaliador |
|---------------------------------------------------------------------------------------------------------|--------------------|----------------------------------|--------------------------|---------------------------|
| Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores                | 2,8              | -                             | -                         |      Poderia ter organizado melhor as cores dos jumpers                     |
| Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo                  | 3              | -                          | -                        |             Temporização está correta e foi medida com celular              |
| Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) | 3              | -                          | -                        | O código implementa as fases corretamente, e está organizado                          |
| Extra: Implmeentou um componente de liga/desliga no semáforo e/ou usou ponteiros no código | 1              |  -                         | -                        | Implementou um buzzer para indicar o semaforo amarelo                           |
| **Pontuação Total: 9,8** |                                                            |  |  ||


<br>

### Avaliador: Davi Ferreira

| Critério                                                                                                 | Contempla (Pontos) | Contempla Parcialmente (Pontos) | Não Contempla (Pontos) | Observações do Avaliador |
|---------------------------------------------------------------------------------------------------------|--------------------|----------------------------------|--------------------------|---------------------------|
| Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores                | 2,8              |    -                       | -                        |                           |
| Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo                  | 3              | -                   | -                        |                           |
| Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) | 3              | -                         | -                    |                           |
| Extra: Implmeentou um componente de liga/desliga no semáforo e/ou usou ponteiros no código | 1            |  -                      | -             |                           |
| **Pontuação Total** |                   9,8                                         |  |  ||

**Comentário**
&emsp;Achei a produção muito bem feita, especialmente os comentários no código. Os tempos estão certos, o buzzer está funcional, e foi utilizado o mdf do semáforo. Em si, essa produção está bem feita.
