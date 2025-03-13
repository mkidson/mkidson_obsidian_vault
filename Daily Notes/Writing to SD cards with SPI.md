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









![[Pasted image 20250312152401.png]]
- 