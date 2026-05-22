# 🍷 Sistema de Monitoramento de Luminosidade, Temperatura e Umidade
## 📌 Checkpoint 02 - Edge Computing
---
## 👥 Integrantes
* **Arthur Caram Fiorese Herrada** - RM: 569578
* **Felipe Ricardo Moreira Aguiar** - RM: 573410
* **Felipi Bandeira de Godoy** - RM: 573741
* **Gustavo Ferreira Silva** - RM: 571675
* **Matheus Medeiros da Cunha** - RM: 572780
---
## 📖 Descrição do Projeto
Este projeto é a continuação do **Checkpoint 01** e expande o sistema de monitoramento da **Vinheria Agnello**, adicionando medição de **temperatura** e **umidade** via sensor DHT11, além de um **display LCD** para exibição dos valores em tempo real.

A proposta surge da necessidade de manter condições ideais de armazenamento dos vinhos, já que temperatura, umidade e luminosidade inadequadas podem comprometer sua qualidade, alterando suas propriedades químicas.

---
## 🎯 Estados do Sistema

* 🟢 **Condição adequada**
* 🟡 **Nível de alerta**
* 🔴 **Condição crítica**

---
## ⚙️ Funcionamento

### 💡 Luminosidade (LDR)
O sensor LDR capta a intensidade luminosa do ambiente e aciona os dispositivos de saída conforme os limites definidos:

| Estado | Ação | Display |
| ------ | ---- | ------- |
| 🟢 Escuro | LED verde aceso | — |
| 🟡 Meia Luz | LED amarelo aceso | "Ambiente a meia luz" |
| 🔴 Muito Claro | LED vermelho + buzzer contínuo | "Ambiente muito CLARO" |

### 🌡️ Temperatura (DHT11)
| Estado | Ação | Display |
| ------ | ---- | ------- |
| ✅ Entre 10°C e 15°C | — | "Temperatura OK / Temp. = XX.XC" |
| 🟡 Acima de 15°C | LED amarelo + buzzer contínuo | "Temp. ALTA / Temp. = XX.XC" |
| 🟡 Abaixo de 10°C | LED amarelo + buzzer contínuo | "Temp. BAIXA / Temp. = XX.XC" |

### 💧 Umidade (DHT11)
| Estado | Ação | Display |
| ------ | ---- | ------- |
| ✅ Entre 50% e 70% | — | "Umidade OK / Umidade = XX%" |
| 🔴 Acima de 70% | LED vermelho + buzzer contínuo | "Umidade. ALTA / Umidade = XX%" |
| 🔴 Abaixo de 50% | LED vermelho + buzzer contínuo | "Umidade. BAIXA / Umidade = XX%" |

> ⚠️ Os valores exibidos no display são a **média de 5 leituras** dos sensores, atualizados a cada **5 segundos**.

---
## 🧰 Componentes
* 1x Arduino (Uno ou similar)
* 1x Sensor LDR
* 1x Sensor DHT11 (temperatura e umidade)
* 1x Display LCD 16x2 (I2C)
* 3x LEDs (verde, amarelo e vermelho)
* 1x Buzzer
* 4x Resistores
* 1x Protoboard
* Jumpers

---
## 📚 Dependências
Instale as seguintes bibliotecas na Arduino IDE antes de compilar:

* **DHT sensor library** — by Adafruit
  `Sketch > Include Library > Manage Libraries > "DHT sensor library"`
* **LiquidCrystal I2C** — by Frank de Brabander
  `Sketch > Include Library > Manage Libraries > "LiquidCrystal I2C"`

---
## 💻 Simulação
* 🔗 Tinkercad (modo editor): *(https://www.tinkercad.com/things/fdk7dbvG8v9-copy-of-cp-02-edge/editel?returnTo=%2Fdashboard%2Fdesigns%2Fcircuits&sharecode=m1oU5wKWgcD8TFwtvYkF2Uy9q-vPq6Rar-hVv5KKZs4)*


<img width="1060" height="505" alt="image" src="https://github.com/user-attachments/assets/00f6093c-a2ac-4379-a4c9-392c09546503" />


---
## 🚀 Como Executar
1. Monte o circuito (simulação ou físico)
2. Instale as bibliotecas listadas em [Dependências](#-dependências)
3. Conecte o LDR na entrada analógica e o DHT11 em uma porta digital
4. Configure LEDs, buzzer e LCD nas portas correspondentes
5. Envie o código para o Arduino
6. Teste variando luminosidade, temperatura e umidade

---
## 🎥 Vídeo
📹 *Vídeo YouTube: (https://youtu.be/LcggcvoSfgo?si=1QaGO-YYriCR2oje
 )*

---
## ⚠️ Desafios
* Integrar múltiplos sensores sem conflitos de leitura
* Calcular médias de 5 leituras com controle de tempo via `millis()`
* Gerenciar a exibição das mensagens no LCD com espaço limitado
* Definir limites e prioridades dos alertas para luminosidade, temperatura e umidade simultaneamente

✔️ Resolvido com testes práticos, uso das funções `millis()` e `map()` da API do Arduino, e ajustes no código.

---
## 📌 Conclusão
O projeto demonstra a evolução do sistema de monitoramento da Vinheria Agnello, incorporando novos sensores e interface de visualização. Reforça a aplicação prática de **Edge Computing**, permitindo decisões em tempo real diretamente no dispositivo para preservar produtos sensíveis como o vinho.

---
