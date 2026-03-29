# STM32 Inversor — DAC + DMA Senoidal

🇧🇷 **Português** | 🇺🇸 [English](#english)

---

## Português

Geração de onda senoidal por DAC com DMA em STM32F4xx, usando tabela LUT de 128 pontos acionada por timers.

### O que faz
- Gera onda senoidal contínua via **DAC + DMA** sem uso da CPU
- Tabela LUT de **128 pontos** calculada em ponto flutuante
- **TIM6** e **TIM7** fornecem o trigger periódico para o DMA
- Frequência configurável pelo prescaler dos timers

### Arquitetura
```
TIM6/TIM7 trigger → DMA → DAC → PA4/PA5 (saída analógica)
LUT[128] = sin(2π·n/128) escalado para 12 bits
```

### Parâmetros
- Resolução DAC: **12 bits** (0–4095)
- Pontos por ciclo: **128**
- Trigger: TIM6 (canal 1) / TIM7 (canal 2)
- Microcontrolador: STM32F4xx

---

## English

Sine wave generation using DAC + DMA on STM32F4xx, with a 128-point LUT triggered by hardware timers.

### What it does
- Generates continuous sine wave via **DAC + DMA** without CPU overhead
- **128-point** LUT computed in floating point
- **TIM6** and **TIM7** provide periodic DMA triggers
- Frequency configurable via timer prescaler

### Architecture
```
TIM6/TIM7 trigger → DMA → DAC → PA4/PA5 (analog output)
LUT[128] = sin(2π·n/128) scaled to 12 bits
```

### Parameters
- DAC resolution: **12 bits** (0–4095)
- Samples per cycle: **128**
- Trigger: TIM6 (ch1) / TIM7 (ch2)
- MCU: STM32F4xx
