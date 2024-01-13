## Description
This demo project evaluates the DAC DMA functionality of the STM32L073RZ:
* The samples of a sinusoid wave (1 period) are precomputed at reset and stored in memory.
* DAC1 is configured to play the precomputed samples through DMA. The samples are loaded cyclically from memory. The CPU is not involved in the transfers.
* The DAC sample rate is determined by TIM6. The frequency of the sinusoid is changed by setting __HAL_TIM_SET_AUTORELOAD on button interrupt. As the sinusoidal wavetable is fixed, the frequency of the sinusoid varies according to the DAC sample rate.
* The user led is toggled with each press. Messages are sent through USART2 at 115200 bauds.

## Usage
Connect a volume adjust potentiometer, decoupling capacitor, and audio amplifier to DAC1 output (PA4) to listen to the generated tones.

## References
Nucleo-64 board user manual: 
https://www.st.com/resource/en/user_manual/um1724-stm32-nucleo64-boards-mb1136-stmicroelectronics.pdf

AN3126 Application note - Audio and waveform generation using the DAC in STM32 products
https://www.st.com/resource/en/application_note/an3126-audio-and-waveform-generation-using-the-dac-in-stm32-products-stmicroelectronics.pdf
