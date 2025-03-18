For use with [[ADC on the DE0-nano]]
# Important to note
- SD seems to use SPI mode 0, but apparently mode 3 works too. The important thing is that you index on the rising edge. I think I'll go for defaulting to low and then sending CS high when we start.
- There is a maximum clock speed. For SDC (high volume) it's 25 MHz, and for MMC it's 20 MHz. I think 20 should be fine.
- Do not supply 5 V, only between 2.7 and 3.6, which should be fine for the 3.3 V we have.
- http://www.chlazza.net/sdcardinfo.html
- http://elm-chan.org/docs/mmc/mmc_e.html

# Commands
- Commands are send to the SD card module using the MOSI line, or Data In. 
- They are 48 bits long, with the following structure
	- Start bits 01
	- 6 bits for the command number
	- 32 bits for the argument (some commands don't take arguments, in which case all bits should be 0)
	- 7 bits containing a Cyclic Redundancy Check (CRC) code, which seems to not be necessary for us, but we may need to use one valid code during initialisation.
	- A stop bit: 1
- 

| Command  <br>Index                                                                                                                                                        | Argument                    | Response | Data | Abbreviation             | Description                                                                                      |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------- | -------- | ---- | ------------------------ | ------------------------------------------------------------------------------------------------ |
| CMD0                                                                                                                                                                      | None(0)                     | R1       | No   | GO_IDLE_STATE            | Software reset.                                                                                  |
| CMD1                                                                                                                                                                      | None(0)                     | R1       | No   | SEND_OP_COND             | Initiate initialization process.                                                                 |
| ACMD41(*1)                                                                                                                                                                | *2                          | R1       | No   | APP_SEND_OP_COND         | For only SDC. Initiate initialization process.                                                   |
| CMD8                                                                                                                                                                      | *3                          | R7       | No   | SEND_IF_COND             | For only SDC V2. Check voltage range.                                                            |
| CMD9                                                                                                                                                                      | None(0)                     | R1       | Yes  | SEND_CSD                 | Read CSD register.                                                                               |
| CMD10                                                                                                                                                                     | None(0)                     | R1       | Yes  | SEND_CID                 | Read CID register.                                                                               |
| CMD12                                                                                                                                                                     | None(0)                     | R1b      | No   | STOP_TRANSMISSION        | Stop to read data.                                                                               |
| CMD16                                                                                                                                                                     | Block  <br>length[31:0]     | R1       | No   | SET_BLOCKLEN             | Change R/W block size.                                                                           |
| CMD17                                                                                                                                                                     | Address[31:0]               | R1       | Yes  | READ_SINGLE_BLOCK        | Read a block.                                                                                    |
| CMD18                                                                                                                                                                     | Address[31:0]               | R1       | Yes  | READ_MULTIPLE_BLOCK      | Read multiple blocks.                                                                            |
| CMD23                                                                                                                                                                     | Number of  <br>blocks[15:0] | R1       | No   | SET_BLOCK_COUNT          | For only MMC. Define number of blocks to transfer  <br>with next multi-block read/write command. |
| ACMD23(*1)                                                                                                                                                                | Number of  <br>blocks[22:0] | R1       | No   | SET_WR_BLOCK_ERASE_COUNT | For only SDC. Define number of blocks to pre-erase  <br>with next multi-block write command.     |
| CMD24                                                                                                                                                                     | Address[31:0]               | R1       | Yes  | WRITE_BLOCK              | Write a block.                                                                                   |
| CMD25                                                                                                                                                                     | Address[31:0]               | R1       | Yes  | WRITE_MULTIPLE_BLOCK     | Write multiple blocks.                                                                           |
| CMD55(*1)                                                                                                                                                                 | None(0)                     | R1       | No   | APP_CMD                  | Leading command of ACMD<n> command.                                                              |
| CMD58                                                                                                                                                                     | None(0)                     | R3       | No   | READ_OCR                 | Read OCR.                                                                                        |








![[Pasted image 20250312152401.png]]




# Pins on the Pmod MicroSD
The VCC pins are connected in series (?) I think best to just supply through the one.

| Pin no. | Name      | SPI name | Description             |
| ------- | --------- | -------- | ----------------------- |
| 1       | ~CS       | CS       | Chip select (inverted?) |
| 2       | MOSI      | MOSI/DI  | MOSI                    |
| 3       | MISO/DAT0 | MISO/DO  | MISO                    |
| 4       | SCK       | SCLK     | Clock                   |
| 5       | GND1      | GND      | Ground                  |
| 6       | VCC1      | VCC      | Power                   |
| 7       | DAT1      | RSV      |                         |
| 8       | DAT2      | RSV      |                         |
| 9       | CD        | n/a      |                         |
| 10      | (NC)      | n/a      |                         |
| 11      | GND2      | GND      |                         |
| 12      | VCC2      | VCC      |                         |

# Pins we can use on the DE0-nano 2x13 header (JP3)

| Pin name | FPGA pin no | MicroSD Pin | Header pin no | Wire colour |
| -------- | ----------- | ----------- | ------------- | ----------- |
| VCC3P3   | n/a         | VCC         | 1             | red         |
| GND      | n/a         | GND         | 26            | black       |
| GPIO_20  | PIN_A14     | CS          | 5             | white       |
| GPIO_21  | PIN_B16     | MOSI        | 6             | orange      |
| GPIO_22  | PIN_C14     | MISO        | 7             | yellow      |
| GPIO_23  | PIN_C16     | SCLK        | 8             | green       |



# Initialisation
- Power on and wait at least 1 millisecond
- Set CS and MOSI to high and toggle SCLK for at least 74 cycles
- Set CS to low and send CMD0
- SD card will send an 8-bit response on MISO which should be 00000001. You can wait for this response as MISO should be high on idle and the response will always start with a 0
- Can then send CMD8, keeping CS low. This will fail on older cards
- The response to CMD8 (or CMD58 if 8 fails) will be the 8-bit response followed by 32 bits of information.
- 