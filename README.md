# 🧠 Arduino Genius (Simon Says) com Controle Bluetooth

## 📋 Descrição do Projeto

Este projeto implementa o clássico jogo de memória "Genius" (também conhecido como Simon Says) na plataforma Arduino. A inovação central é a substituição da interface tradicional de botões físicos pela **comunicação serial sem fio via Bluetooth**, permitindo que o jogador controle o jogo através de um aplicativo móvel (como o Bluetooino).

O objetivo é reproduzir a sequência crescente de luzes e sons gerada pelo sistema.

## ✨ Funcionalidades

* **Jogo de Sequência:** Gera e armazena sequências de até 100 passos.
* **Feedback Audiovisual:** Usa 4 LEDs e um Buzzer para reproduzir as sequências e indicar as jogadas.
* **Controle Bluetooth:** Lê os comandos do jogador via módulo HC-05 ou HC-06.
* **Game Over:** Rotina audiovisual para sinalizar o erro e o fim do jogo.

## 🛠️ Hardware Necessário

* 1 x Placa Arduino UNO ou Nano
* 1 x Módulo Bluetooth (HC-05 ou HC-06)
* 4 x LEDs (Preferencialmente Amarelo, Azul, Vermelho, Verde)
* 4 x Resistores de 220 Ohms (para os LEDs)
* 1 x Buzzer ou Alto-falante ativo
* Fios e Protoboard

## 🔌 Diagrama de Conexão

### Mapeamento de Pinos (Físico)

| Componente | Pino do Arduino | Função no Código (Índice) | Caractere Bluetooth (Entrada) |
| :--- | :--- | :--- | :--- |
| **LED 1 (Ex: Amarelo)** | D2 | 0 | '0' |
| **LED 2 (Ex: Azul)** | D4 | 1 | '1' |
| **LED 3 (Ex: Vermelho)** | D6 | 2 | '2' |
| **LED 4 (Ex: Verde)** | D8 | 3 | '3' |
| **Buzzer** | D12 | - | - |
| **Bluetooth RX (Módulo)** | **D10 (TX Virtual)** | - | - |
| **Bluetooth TX (Módulo)** | **D11 (RX Virtual)** | - | - |
| **Bluetooth VCC** | 5V | - | - |
| **Bluetooth GND** | GND | - | - |

### Esquema Fritzing

A imagem a seguir ilustra as conexões principais entre o Arduino e os periféricos, com destaque para o módulo Bluetooth.

## 📱 Configuração do Aplicativo Bluetooth (Ex: Bluetooino)

Para jogar, configure um layout com 4 botões no aplicativo de controle:

| Botão no App (Visual) | Valor de Envio (Caractere ASCII) |
| :--- | :--- |
| Amarelo | `0` |
| Azul | `1` |
| Vermelho | `2` |
| Verde | `3` |

O Arduino monitora a porta serial e usa estes caracteres para validar a jogada do usuário.
