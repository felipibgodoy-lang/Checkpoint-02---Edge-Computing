# 🍷 Vinheria Agnello — Sistema de Monitoramento Inteligente

> **Edge Computing & Computer Systems — Checkpoint 02**  
> FIAP · Engenharia de Software · 2026

---

## 📖 Sobre o Projeto

A **Vinheria Agnello** é uma loja tradicional de vinhos que está expandindo suas operações para o e-commerce. Para garantir a qualidade dos produtos, é fundamental monitorar as condições ambientais do estoque, já que temperatura, umidade e luminosidade impactam diretamente na conservação dos vinhos.

Este projeto implementa um sistema embarcado com **Arduino** capaz de monitorar em tempo real as condições do ambiente e emitir alertas visuais e sonoros quando algum parâmetro sai da faixa ideal.

---

## ✅ Funcionalidades

### 💡 Luminosidade (LDR)
| Condição | LED | Display | Buzzer |
|----------|-----|---------|--------|
| Escuro | 🟢 Verde | — | ❌ |
| Meia Luz | 🟡 Amarelo | "Ambiente a meia luz" | ❌ |
| Muito Claro | 🔴 Vermelho | "Ambiente muito CLARO" | ✅ Contínuo |

### 🌡️ Temperatura (DHT11)
| Condição | LED | Display | Buzzer |
|----------|-----|---------|--------|
| Entre 10°C e 15°C | — | "Temperatura OK / Temp. = XX.XC" | ❌ |
| Acima de 15°C | 🟡 Amarelo | "Temp. ALTA / Temp. = XX.XC" | ✅ Contínuo |
| Abaixo de 10°C | 🟡 Amarelo | "Temp. BAIXA / Temp. = XX.XC" | ✅ Contínuo |

### 💧 Umidade (DHT11)
| Condição | LED | Display | Buzzer |
|----------|-----|---------|--------|
| Entre 50% e 70% | — | "Umidade OK / Umidade = XX%" | ❌ |
| Acima de 70% | 🔴 Vermelho | "Umidade. ALTA / Umidade = XX%" | ✅ Contínuo |
| Abaixo de 50% | 🔴 Vermelho | "Umidade. BAIXA / Umidade = XX%" | ✅ Contínuo |

> 📊 Os valores exibidos no display são a **média de 5 leituras**, atualizados a cada **5 segundos**.

---

## 🛠️ Componentes Utilizados

| Componente | Descrição |
|------------|-----------|
| Arduino Uno | Microcontrolador principal |
| DHT11 | Sensor de temperatura e umidade |
| LDR | Sensor de luminosidade |
| LCD 16x2 (I2C) | Display de mensagens |
| LED Verde | Indicador de luminosidade OK |
| LED Amarelo | Indicador de alerta (temp/luz) |
| LED Vermelho | Indicador crítico (umidade/luz) |
| Buzzer | Alerta sonoro |
| Resistores | 220Ω (LEDs), 10kΩ (LDR) |

---

## 📦 Dependências

Instale as seguintes bibliotecas na Arduino IDE antes de compilar:

- **DHT sensor library** — by Adafruit  
  `Sketch > Include Library > Manage Libraries > "DHT sensor library"`

- **LiquidCrystal I2C** — by Frank de Brabander  
  `Sketch > Include Library > Manage Libraries > "LiquidCrystal I2C"`

- **Wire** *(já inclusa na IDE do Arduino)*

---

## ▶️ Como Reproduzir

### Simulação Online
Acesse a simulação no **Wokwi** pelo link disponível no repositório.

### Hardware físico
1. Clone este repositório:
   ```bash
   git clone https://github.com/seu-grupo/vinheria-agnello-cp02.git
   ```
2. Abra o arquivo `vinheria_agnello.ino` na Arduino IDE.
3. Instale as bibliotecas listadas em [Dependências](#-dependências).
4. Monte o circuito conforme o diagrama em `/docs/circuito.png`.
5. Selecione a placa **Arduino Uno** e a porta correta.
6. Faça o upload do código.

---

## 🗂️ Estrutura do Repositório

```
vinheria-agnello-cp02/
├── src/
│   └── vinheria_agnello.ino    # Código-fonte principal
├── docs/
│   └── circuito.png            # Imagem do circuito montado
├── simulation/
│   └── wokwi_link.txt          # Link para simulação no Wokwi
├── video/
│   └── demo_link.txt           # Link para o vídeo explicativo
└── README.md
```

---

## 👥 Integrantes do Grupo

| Nome | RM |
|------|----|
| Arthur | RM 576849 |
| Felipe Ricardo Moreira Aguiar | RM 573410 |
| Felipi Bandeira de Godoy | RM 573741 |
| Gustavo Ferreira Silva | RM 571675 |
| Matheus Medeiros da Cunha | RM 572780 |

---

## 📚 Referências

- [Documentação DHT11 — Adafruit](https://learn.adafruit.com/dht)
- [Função millis() — Arduino Reference](https://www.arduino.cc/reference/en/language/functions/time/millis/)
- [Função map() — Arduino Reference](https://www.arduino.cc/reference/en/language/functions/math/map/)
- PANDELL, Alexander J. *How Temperature Affects the Aging of Wine*. University of California.

---

<div align="center">
  <sub>Desenvolvido com ❤️ para a disciplina de Edge Computing & Computer Systems — FIAP 2026</sub>
</div>
