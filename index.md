---
layout: home
title: FPGA VGA Driver Project
tags: fpga vga verilog
categories: demo
---

For my FPGA Project I decided to attempt to make a moving snippet from a game of Tetris.  
As this is my first time working with Verilog code it was a bit of a learning curve with a lot of trial and error to get the final project working.  

## **VGA Design**
### **Project Summarie**
//Text//
//Project Summary Image//  

### **Template Code**
I took inspiration from both the VGAStripes and VGAColorCycle examples, I combined the Logic of the Stripes example with the states of the ColorCycle exsample.    
  
*//ColorCycle Example//*  
//ColorCycleSnippet Image//  
  
*//Stripes Example//*  
//ColorStripesSnippet Image//

There where a few things that i had to change to make my idea come to life, first I exsperamented with the color stripes to get a static image of the blocks all lined up and then started incoperating the ColorCycle states into my project. The code working by setting a boundry inside the display aread and changibg that areas color on the display to one of my choosing, this is done for each and every bocks row and column 
//Static Code Image// 

To make the cyan block move from the top of the screan every clock cycle, slowly towards the right hand side of the screen where the completed line will be deleted and the blocks above will fall down 1 row, I incoperated the states from the ColorCycle example, however after making a few states with the original code that i created i noticed that i was at 500+ lines of code and i was only half way through with the states and thought there had to be a better way to do this without writing a thousand lines of code.
//Multiple states Images//

I found my solution with functions, Instaed of writing each and ever line over and over in the states, the only thing that would change in the states is the I block as it it the only one moving and the rest are static, This made the code go from 500 lines to around 150 lines
//Function Code Image//
//I Block States Image//
//Static Blocks states Image//

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

