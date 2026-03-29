# stm32-inversor

Controle de inversor trifásico com geração de sinal senoidal via DAC com DMA no STM32F4xx.

## Descrição

Projeto de acionamento de inversor trifásico. Utiliza o DAC com DMA para gerar sinais senoidais a partir de uma tabela de 128 pontos, sincronizados por timers de hardware (TIM6 e TIM7).

## Hardware

- Microcontrolador: STM32F4xx (STM32CubeMX gerado)
- Saídas DAC com DMA

## Periféricos utilizados

| Periférico | Função |
|------------|--------|
| DAC ch1 + DMA | Geração senoidal canal 1 |
| DAC ch2 + DMA | Geração senoidal canal 2 |
| TIM6 | Trigger DAC canal 1 |
| TIM7 | Trigger DAC canal 2 |
| USART2 | Comunicação serial |

## Tabela senoidal

128 amostras de 12 bits (0–4095), centrada em 2048.

## Estrutura do projeto

```
Inversor_ARM/
├── Src/
│   ├── main.c
│   ├── stm32f4xx_hal_msp.c
│   ├── stm32f4xx_it.c
│   └── system_stm32f4xx.c
├── Inc/
├── Drivers/
└── Inversor_ARM.ioc
```

## IDE

STM32CubeIDE / Atollic TrueSTUDIO

## Escola

Centro Tecnológico Liberato — Novo Hamburgo/RS
