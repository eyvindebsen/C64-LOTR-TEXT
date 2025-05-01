# C64-LOTR-TEXT
"The Lord Of The Rings" text on 3 disks.

This is an experiment to get the entire first book of J.R.R. Tolkiens 'Lord of the rings', in compressed format for the Commodore 64.
For now, spending 3 floppy sides. (3*160kb)
Raw text is 980kb, 'compressed' to 397kb, including decoder on disk 1.

The raw input text is provided in the file "01 - The Fellowship Of The Ring-new.txt"

The program works by reading 1 bit from the input buffer to determine if the next thing in the input buffer is either a special char, or a word/string.
If its a word, read 4 more bits to determine which wordbank to access (2-16)
Depending on the wordbanks size, a fixed number of bits is read to determine the wordnumber. (In worst case 12 bits to get a number from 0..4095. Wordbank 7 usually gets this big.)
In this way any word is using a max. 16 bits, no matter the wordlength. Ofcourse the word itself is stored in the executeable, but in a 5-bit stream.

If it is a special char, read 5 more bits to get a number between 0..31 to determine which special char it is. (To be optimized)

How to run
-----------
Load disk 1. When asked for a part, insert the disk you want to read from.
There are 3 disks, side a, b and c.

This could save your night if the internet is down ;)

Takes about an hour to print the entire story at normal c64 speed. (Decoder is in ASM, so only slowdown for now is the read from disk, and print to screen.)
This ia about a full c64 screen every 2nd second.
Several days of joyfull reading.

How to use the program.
-----------------------
When started, a full screen of text will be displayed.

A menu in the bottom will give you the options to
1. Print a page of text. This pauses every page.
2. Continue printing all text. Interrupt this with any keypress.
3. Changes text color.
4. Shows the second menu.
5. Change background color.
6. Change foreground color.
7. For future use; search?
8. Close book and end.
