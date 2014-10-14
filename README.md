LAB3_ECE382
===========

Lab 3 for ECE 382 - SPI - "I/O"


###Objective and Purpose
The purpose of this lab is to understand how to minupulate pixels to perform a desired task or display desired image.

Required Functionality [COMPLETED]:
  
   Required functionality: Create a block on the LCD that is 8x8 pixels. 
   The location of the block must be passed into the subroutine via r12 and r13.
   A functionality: Move the 8-pixel block one block in the direction of the pressed button (up, down, left, right).

  
###Implementation  

  Basic Understanding of the following table will allow implementation of required functionality.
  
![alt text](https://raw.githubusercontent.com/vipersfly23/LAB3_ECE382/master/PreLab3.GIF "PreLab3 Data Table")

###Code

Register Definition:

    * R10 - Keeps track of up/down address. 
    * R11 - Keeps track of left/right address.
    * R12 - R10 is modified and passed into R12.
    * R13 - R11 is modified and passed into R13.

#####Result:
  Data/Command:
  
  ![alt text](https://raw.githubusercontent.com/vipersfly23/LAB3_ECE382/master/datacmd.jpg "Command/Data Bit")

  
  8 data bit:
  
   ![alt text](https://raw.githubusercontent.com/vipersfly23/LAB3_ECE382/master/8data.GIF "8data bit")

Line | R12 | R13 | purpose
--- | --- | --- | ---
66  |0x0001|0x00E7|Beam with 2 pixel holes
276 |0x0000|0x00B0| select rows
288 |0x0000|0x0010|select columns
294 |0x0000|0x0000|copies stack

Line | Command/Data | 8-bit packet
--- | --- | --- 
66  |0x0001|0xE7
276 |0x0000|0xB0
288 |0x0000|0x10
294 |0x0000|0x00


The main portion of the Lab was given by instructor which draws a 1 pixel wide by 8 pixel high, with a two pixel hole in the middle.


###Debugging/Testing

#####Methodology

  
    My methodology was dividing and conquered. I knew that if I can manipulate the left/right/up/down function if I understood 
    which registered stored the address. Once I figured that out, I simply added the buttons in using the already given code 
    but looked at different pins. I then simply added if statements and kept the set up the same. The main purpose of the "if"
    statements was so I could change the task of each button.
   
    My biggest issue was understaning the given code. It took awhile to figure out what I had to do to adjust the code so
    that it would work accordingly. After figuring out the code, it was simple coding.

#####Commit 1

  This commit was to add the finished code. (only about 20 lines were added)
  
#####Commit 2
  
   Added additional pictures / diagrams
   
#####Commit 3
    
  Added more pictures.

#####Commit 4
  
  Added more pictures.
    
****All other commits are either to add comments to the program or to update the README file****

#####Testing:

The testing could be verified by the image below. It shows the previous location of the box, by using the directional pads
I was able to draw a H:

 ![alt text](https://raw.githubusercontent.com/vipersfly23/LAB3_ECE382/master/result.jpg "Results")


###Conclusions/Lessons Learned
  In conclusion the program was a success. The understanding of command/data bits were greatly enhanced. 
  Understanding of how input and output pins are used in the MSP430 has greatly improved. Also the lab itself was success.
  Biggest lesson learned is that understanding a given code is the most important step, and it must be achieved before trying
  to add changes to the code.


####Documentation:
  I used the ECE382.com website to access lab information and used the website to obtain the instruction sheet for the assembly
  language. No other help received.
