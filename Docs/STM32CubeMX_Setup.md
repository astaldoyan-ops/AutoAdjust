Для створення .ioc файлу в STM32CubeMX:

1. Відкрити STM32CubeMX
2. New Project -> Board Selector: NUCLEO-F446RE (або вибрати STM32F446RETx)
3. Налаштувати периферію:
   - RCC: HSE/HSI за потреби
   - SPI1: Mode = Full-Duplex Master, Hardware NSS = Disable, Prescaler під частоту
   - ADC1: IN0 включити, режим безперервний/одиночний за алгоритмом
   - USART2: Asynchronous, 115200
   - TIM2: базовий таймер для циклу автоналаштування
   - GPIO: PA4, PB0 - Output Push Pull для CS
4. Project Manager:
   - Project Name: AutoAdjustPDRegulator
   - Project Location: C:\Projects\AutoAdjustPDRegulator\Firmware
   - Toolchain: STM32CubeIDE / MDK-ARM / EWARM (на вибір)
5. Generate Code

Після генерації можна додати драйвер для MCP4251 (функції WritePot(channel, value)) та алгоритм автопідбору P,D.
