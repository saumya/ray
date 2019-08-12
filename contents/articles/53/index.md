---
title: Vi/Vim comands
author: saumya
date: 2015-8-6
template: article.pug
---

           
 
First of all there are 2 modes. `Insert` and `Command` . By default one is in the command mode.
```
i : to move to insert mode
esc : to move out from insert mode
```
Following is a set of commands I use in a regular basis.
```
a : append : start after cursor
i : insert : start before cursor

w : move forward word by word
b : move backwars word by word

ctrl+F : scroll forward 1 screen
ctrl+B : scroll backward 1 screen
ctrl+D : scroll forward 1/2 screen
ctrl+U : scroll backward 1/2 screen

ctrl+E : scroll forward 1 line
ctrl+Y : scroll backward 1 line

ctrl+H : move to top line
ctrl+M : move to middle line
ctrl+L : move to last line

/ : search for pattern : forward from cursor
? : search for pattern : backwards from cursor

f,F : search inline forward,backward
t,T : move cursor to occurance of the character forwar,backward
; , , : repear last find command forward and backward

ctrl+G : print line info
G : move the cursor by line number
```     
`ctrl+L` : Redraw the screen : `Remember the screen in just a buffer of texts`          
Configuring vi :
```
set nu : show line numbers
set nowrapscan : search does not wrap TOP or BOTTOM
```





Happy editing.



