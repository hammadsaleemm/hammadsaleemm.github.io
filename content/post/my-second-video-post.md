---
title: "Logo Print Summary"
date: 2021-04-20T19:34:48+05:00
draft: false
images: ""
---
Explanation:
-
Most of the files remain same as they were in the previos task. But for this we used C language to print "NUST" USING " * " on the screen.

First we built the stack. It is useful because it return the data every time function completes and also returns the control. We reserved 16kb of memeory for the stack. ESP regster is used as stack pointer to give the address. To switch to 64 bit we used Long mode for which the code is written in the file.

Then we checked for multiboot, cpu-id,long-mode and error code. Linking btw virtual and physical address helped us to remove the memory loset issue. This process is known as paging in which we added page-tables in the previous main file.

Then, we added another file in src known as main64.asm ehich now contain 64 bits instead of 32 bits. We started long-mode labels. In these labels we passed 0 to all data registers so that they can function properly now.


After all these setups, I started writing the C code to print NUST on the screen. We built main.c file and kernel-main fnction is given the link in main6r also.


In Kernel we have three  functions:
   Printclear to clear the screen.
   Setcolor to set background and front color.
   PrintStr to write some characters or text.

In print.h, we defined our printing interface.

We make print.c implementing file which implements print.h also. char struct is used to hold the character on the memory device. Buffer is simply refernce to the video memory. We added two varibale rows and coloumns to keep track of rows and coloumns during printing and color for back and front color.

In print clear, we looped from 0 to  the total number of rows and then called clearrow for each row to print empty character. Same for colomnclear,too.

In printchar, we print character but first we defined check whther it is newline or not. If it is newline character the newline function calls on which works on moving to the next line by checking if it is not a new line.

After all this setting, I updated makefile to get the c commmands and succeded in printing the NUST onto the screen.


OUTPUT:
-
![NUST](/images/NUST.PNG)
