---
title: "Ok-Print and building OS Summary"
date: 2021-04-20T19:34:48+05:00
draft: false
images: ""
---

Software Used:
-
QEMU, DOCKER, VISUAL STUDIO CODE, HUGO, 

Explanation:
-
First I downloaded docker and set up the required files on the visual studio code. First to print Ok on screen we used some packages using RUN commmand. I used NASM to compile our assembly code. To get the final file I used grub package.

In the src folder we contained our two files header.asm and main.asm. We used two label for start and end of header. Here we added magic number and length. We named it as section which helped us in the final stage of linking. We added two dw's and dd at the end set to zero to show that we dont have any more data.

Main.asm file is acting as a entry file with start as entry point. In start label we printed OK. mov in it is used to move the data that is 'ok'.

hlt is used to freeze the cpu.

Linker.ld is used to link all the files. Entry is used as entrypoint named as start. We then defined each section individually. Boot folder is used to keep the multiboot header we defined in header.asm

grub.cfg is used to get the iso file because in most cases if you want to put your os in USB you need iso file.

Makefile is used to handle your file and ensured only build can be rebuild and no other than these.

Then we used some commands to move to the root and then we used make to form kernal file.

To print Ok we then needed qemu which we downloaded and after running its command we succeded in creating our own OS.

OUTPUT:
-
![OK](/images/OK.PNG)
