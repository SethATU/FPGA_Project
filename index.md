---
layout: home
title: FPGA VGA Driver Project
tags: fpga vga verilog
categories: demo
---  

For my FPGA project I built a looping snippet of Tetris that runs on a Basys3 board and displays over VGA  
A cyan (I) block slides across the top, rotates then drops down into a gap, completes a line and the line is cleared so the blocks above fall down one row  
This was my first time working with Verilog, so there was a lot of trial and error before the final project worked 

## **VGA Design**  
### **Project Setup**  
The project was created in Vivado for the Basys3's Artix-7 FPGA, using Verilog as the coding language and the Vivado Simulator for simulation  
The top module is VGATop which connects three blocks:
- A clock that generates the pixel clock from the board's 100 MHz oscillator
- VGASync which produces the VGA timing signals and the color module 
- ColourStripes which decides the colour of each pixel  
The Basys3_Master constraints file maps the designs ports to the boards clock, reset and VGA connector pins  
Testbench in the simulation sources drives VGASync and ColourStripes the design flow was:
- write the Verilog, simulate, synthesise, implement, generate the bitstream and program the board  

### **Project Summarie**
Project Summary
<img width="1639" height="734" alt="image" src="https://github.com/user-attachments/assets/52ec145f-11b5-48cb-8c58-db4206ac2a59" />  

Project Sources  
<img width="491" height="491" alt="image" src="https://github.com/user-attachments/assets/3330f4c9-95a4-47da-aa63-aac1741cebe1" />

### **Template Code**
A VGA monitor draws its picture one pixel at a time, left to right and top to bottom  
Two sync signals (hsync and vsync) tell the monitor when to start a new line and a new frame  
The colour of each pixel is sent as red, green and blue The Basys3 provides 4 bits per color which gives 12 bit color   
  
In the template VGASync counts through the pixels of each line and the lines of each frame producing the sync pulses along with the row and col of the pixel currently being drawn    
The color module then only has to what color should the pixel at (col, row) be   
Its registered on the clock edge and sent to the red, green and blue outputs  

I was given two examples to work from 
- ColourCycle is a state machine (BLACK, RED, YELLOW, GREEN, CYAN, BLUE, MAGENTA, WHITE) with a counter, each time the counter reaches COUNT_TO the next state is selected, so the whole screen changes colour
- ColourStripes has no states, it compares col against ranges 80 pixels wide and picks a color for each range, giving vertical stripes


ColourCycle Example  
<img width="702" height="525" alt="image" src="https://github.com/user-attachments/assets/5e8a3069-d70f-4a3b-a25e-4b4db0e78ee3" />

ColourStripes Example  
<img width="540" height="559" alt="image" src="https://github.com/user-attachments/assets/25054a61-544a-48e8-880e-c8910add1f4b" />

### **Simulation**
Explain the simulation process. Reference any important details, include a well-selected screenshot of the simulation. Guideline: 1/2 short paragraphs.
### **Synthesis**
Describe the synthesis and implementation processes. Consider including 1/2 useful screenshot(s). Guideline: 1/2 short paragraphs.
### **Demonstration**
Perhaps add a picture of your demo. Guideline: 1/2 sentences.

## **My VGA Design Edit**
Introduce your own design idea. Consider how complex/achievabble this might be or otherwise. Reference any research you do online (use hyperlinks).
### **Code Adaptation**
Briefly show how you changed the template code to display a different image. Demonstrate your understanding. Guideline: 1-2 short paragraphs.
### **Simulation**
Show how you simulated your own design. Are there any things to note? Demonstrate your understanding. Add a screenshot. Guideline: 1-2 short paragraphs.
### **Synthesis**
Describe the synthesis & implementation outputs for your design, are there any differences to that of the original design? Guideline 1-2 short paragraphs.
### **Demonstration**
If you get your own design working on the Basys3 board, take a picture! Guideline: 1-2 sentences.

## **More Markdown Basics**
This is a paragraph. Add an empty line to start a new paragraph.

Font can be emphasised as *Italic* or **Bold**.

Code can be highlighted by using `backticks`.

Hyperlinks look like this: [GitHub Help](https://help.github.com/).

A bullet list can be rendered as follows:
- vectors
- algorithms
- iterators

Images can be added by uploading them to the repository in a /docs/assets/images folder, and then rendering using HTML via githubusercontent.com as shown in the example below.

<img src="https://raw.githubusercontent.com/melgineer/fpga-vga-verilog/main/docs/assets/images/VGAPrjSrcs.png">

