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

| Counter | Action on edges of SCLK.<br>Note that if the counter changes on a posedge, the value when evaluating counter at that posedge is still the previous value |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 0       | State is idle, then when CS goes low, MISO goes low immediately.<br>On the next CLK posedge, SCLK goes from high to low.                                 |
| 0       | negedge: Nothing<br>posedge: Counter increases to 1 (same every cycle)                                                                                   |
| 1       | negedge: Nothing<br>posedge: Nothing                                                                                                                     |
| 2       | negedge: Start sending ADD on MOSI, starting with ADD2<br>posedge: ADC reads ADD2                                                                        |
| 3       | negedge: Send ADD1<br>posedge: ADC reads ADD1                                                                                                            |
| 4       | negedge: ADC sends data, MSB first<br>posedge: Read MISO line                                                                                            |
| 5       | negedge: Nothing<br>posedge: Read MISO line                                                                                                              |
| 6       | negedge: Nothing<br>posedge: Read MISO line                                                                                                              |
| 7       | negedge: Nothing<br>posedge: Read MISO line                                                                                                              |
| 8       | negedge: Nothing<br>posedge: Read MISO line                                                                                                              |
| 9       | negedge: Nothing<br>posedge: Read MISO line                                                                                                              |
| 10      | negedge: Nothing<br>posedge: Read MISO line                                                                                                              |
| 11      | negedge: Nothing<br>posedge: Read MISO line                                                                                                              |
| 12      | negedge: Nothing<br>posedge: Read MISO line                                                                                                              |
| 13      | negedge: Nothing<br>posedge: Read MISO line                                                                                                              |
| 14      | negedge: Nothing<br>posedge: Read MISO line                                                                                                              |
| 15      | negedge: Nothing<br>posedge: Read MISO line                                                                                                              |
| 0       | negedge: ADC sends first of 4 zeroes on MISO<br>posedge: Nothing                                                                                         |
| 1       | Repeat as before                                                                                                                                         |
