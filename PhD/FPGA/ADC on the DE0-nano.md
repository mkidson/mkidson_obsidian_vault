# SPI Interface for the ADC
## Inputs

| Name | Function    | Connects to       |
| ---- | ----------- | ----------------- |
| clk  | Input clock | pll clock divider |
| dout | MISO        | PIN_A9 - ADC MISO |
## Outputs

| Name      | Function                            | Connects to        |
| --------- | ----------------------------------- | ------------------ |
| din       | MOSI                                | PIN_B10 - ADC MOSI |
| sclk      | ADC clock                           | PIN_B14 - ADC sclk |
| cs        | Chip Select                         | PIN_A10 - ADC CS   |
| data_out  | Output ADC value                    |                    |
| clock_out | Clock cycle per ADC cycle (16 sclk) |                    |
## Internal variables

| Name      | Function                                               |
| --------- | ------------------------------------------------------ |
| data_temp | Holds data while compiling from bitstream              |
| count     | 4-bit counter tracking the progress of the interaction |
| ADD[2:0]  | Address used to select which pin to read from          |

## Step by step process

- Initialise the interface by setting :

| Var       | Init value    |
| --------- | ------------- |
| count     | 0000          |
| cs        | 0             |
| ADD[2:0]  | 000 (depends) |
| clock_out | 0             |
| data_out  | 000000000000  |
| data_temp | 000000000000  |
- Some trigger sets CS to 0 and the SCLK goes from high to low, starting its first cycle of 16 (after about 5 ns, at most 30 ns)
- On the posedge of the 3rd cycle, we start sending ADD[2:0] to the MOSI line, one bit at a time