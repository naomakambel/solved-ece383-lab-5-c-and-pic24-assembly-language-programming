Download Link: https://assignmentchef.com/product/solved-ece383-lab-5-c-and-pic24-assembly-language-programming
<br>



<em>Goals: The goals of this lab are to introduce students to basic C language programming and equivalent PIC24 assembly language programming. </em>

<em>Introduction </em>

This lab introduces basic C language programs and equivalent PIC24 assembly language programs. The tasks in this lab are:

<ul>

 <li>Implement programming tasks using the C language.</li>

 <li>Implement equivalent programs using the PIC24 assembly language.</li>

</ul>

This lab requires you to capture portions of the screen. The lab computers use the Windows operating system. This includes the “Snipping Tool” that may be used to capture portions of the screen. Other third party tools are also available.

As always, read through the entire lab and scan any supplied files before starting work. The reporting requirements have you verify computations performed by the assembly language or C program. In all cases, make it easy for the TA to verify your computations by showing your work. <strong>NOTE</strong>: When writing MPLAB assembly language programs, do not use variable names <strong>a</strong> or <strong>b</strong> as these are reserved names.

This lab will make use of several C header files discussed in the text. These files should be located in the <em>C:microchiplibinclude</em> directory on the lab computers. These files were installed as a part of the PIC24 library available on the class website.

<h1>1.     Prelab</h1>

For this lab assignment, the programs for <strong>Task 1 and 2</strong> should be completed as a pre-lab assignment prior to your assigned lab time.

<strong>TA check: As soon as you enter lab, provide the TA with a pre-lab report that includes the complete C and assembly language programs. Lab  time  will  be  devoted  to  debugging  the program  execution  and  correcting  any  errors  noted  by  the  lab  instructor. Make sure your group member names and date are on the pre-lab report. </strong>

<h1>2.     TASK 1: Basic C arithmetic operations</h1>

For this task you will create multiple C and assembly language projects implementing arithmetic operations. Perform the following steps:

<ul>

 <li>Start the MPLAB IDE. Use <em>Project-&gt;Project Wizard</em> for the creation of an MPLAB project.

  <ul>

   <li>Step One: Select the device <em>PIC24HJ128GP502</em>.</li>

   <li>Step Two: Select the Active Toolsuite as <em>Microchip C30 Toolsuite</em>.</li>

   <li>Step Three: <em>Create a New Project File</em> in a unique directory on the local hard disk (<em>C:temptask1.mcp</em> as an example).</li>

   <li>Step Four: Skip the addition of existing files to the project.</li>

  </ul></li>

 <li>After the project is open, use <em>Project-&gt;Build Options</em> to add the <em>C:microchiplibinclude </em>directory to the <em>Include Search Path</em> directory as shown in Figure 1 below.</li>

</ul>




<strong>Figure 1. Include Search Path Directory. </strong>

<ul>

 <li>Enter the C program below and save it with the name <em>c</em> as a part of the project.</li>

</ul>

#include “pic24_all.h”




uint16 u16_a, u16_b, u16_c, u16_d; uint8  u8_x,  u8_y,  u8_z;




void main(void) {   u8_x=0xFF;   u8_y=0x01;   u16_a = 0xFFFF;   u16_b = 0x0001;




u8_z=u8_x+u8_y;

u16_d=(uint16) u8_x + (uint16) u8_y;

u16_c=u16_a+u16_b;

}

<ul>

 <li>Use <em>Project-&gt;Build All</em> to compile the program. If the source file is not already open, double-click on the <em>c </em>source file to open it.</li>

 <li>After the project is compiled, use <em>View-&gt;Program Memory</em> and open the program memory window. Scroll the window until you find your program in memory. Your program should begin at location 0x200.</li>

 <li>Use <em>View-&gt;File Registers</em> to view data memory. Scroll to location 0x800, which is where your variables will start.</li>

 <li>Use <em>View-&gt;</em><em>Special Function Registers </em>to view the special function registers (these will appear as WREG0WREG15, etc).</li>

 <li>Open a watch window <em>(View-&gt;</em><em>Watch) </em>and use <em>Add </em><em>Symbol </em>to watch variable values of the all the program variables. Use <em>Add SFR</em> to watch the <strong>SR </strong>(status register) special function register value.</li>

 <li>Use <em>Debugger-&gt;Select Tool-&gt;MPLAB Sim</em> to select the MPLAB Simulator.</li>

 <li>Use <em>Debugger-&gt;Step Into</em> <em>(F7) </em>to single step through the program. Watch both the memory locations and watch window locations, and correlate their changing values with the instructions being executed. For all three of the arithmetic operations, record the value of the result and the value of the sign/negative (N), carry (C), zero (Z), and overflow (V) flags. The value of the flags can be determined from the SR register and are also indicated at the bottom of the MPLAB IDE.</li>

</ul>

<strong>TA check</strong>: <strong>Show the TA the task 1 results including the final state of the program, data memory, and the watch window. Use a screen capture tool to capture these windows and include them in your lab report. Include your source language program in your lab report.</strong>

<h1>3.     TASK 2: C Program check_val</h1>

Create an MPLAB project (<em>task2.mcp</em>) containing a C program (<em>task2.c</em>) that counts the number of one bits in a 16-bit unsigned integer named <strong>check_val</strong>. The count value should be stored in an 8-bit unsigned variable named <strong>ones_count</strong>. The program should also determine which is the first bit set in the <strong>check_val </strong>variable. The location of the first bit set should be stored in an 8-bit unsigned variable named <strong>first_one</strong>. For example, if <strong>check_val</strong>=0xF508 then the computed values should be <strong>ones_count</strong>=7 and <strong>first_one</strong>=3.

Hint: Use a for loop and shift right every iteration of the loop to simplify testing of a bit value. You must download your program to your PIC24 hardware (i.e. the Microstick II) and demonstrate the execution of your program on hardware to the TA.

<strong>TA check: Show the TA the task 2 results including the final state of the program, data memory, and the watch window. Use a screen capture tool to capture these windows and include them in your lab report. Include your source language program in your lab report. </strong>

<h1>4.     TASK 3: Assembly Language Program check_val</h1>

Create an MPLAB project (<em>task3.mcp</em>) containing an assembly language program (<em>task3.s</em>) that implements the equivalent of task 2.

You must download your program to your PIC24 hardware and demonstrate the execution of your program on hardware to the TA.




<strong>TA check: Show the TA the task 3 results including the final state of the program, data memory, and the watch window. Use a screen capture tool to capture these windows and include them in your lab report. Include your source language program in your lab report. </strong>

<h1>5.     TASK 4:  Assembly to C Example</h1>

Create a new assembly project and input the assembly code as shown below. See the program results after executing the program. Create an MPLAB project (<em>task4.mcp</em>) containing a C program (<em>task4.c</em>) that implements the equivalent of the assembly program.

.include “p24Hxxxx.inc”

.global __reset




.bss           ; Uninitialized data section

; Variables start at location 0x0800

x:       .space 2     ; Allocating space (two bytes) to variable. y:       .space 2     ; Allocating space (two bytes) to variable. count:   .space 1     ; Allocating space (one byte) to variable.




;……………………………………………………………..

; Code Section in Program Memory

;……………………………………………………………..




.text                     ; Start of Code section

__reset:                   ; first instruction located at __reset label         mov #__SP_init, w15      ; Initialize the Stack Pointer         mov #__SPLIM_init,W0

mov W0, SPLIM            ; Initialize the stack limit register

; __SP_init set to be after allocated data




; User Code starts here.

<table width="325">

 <tbody>

  <tr>

   <td colspan="2" width="325">        mov #0x3, w0</td>

  </tr>

  <tr>

   <td width="96">    top:      next:   next2: </td>

   <td width="229">mov.b wreg, count  mov #0x1, w1  mov w1, x  mov #0x3, w2  mov w2, ycp0.b count bra z, donecp w1, w2 bra nz, next inc w2, w2 mov w2, ycp w1, w2 bra GEU, next2 add #0x2, w1 mov w1, x dec.b count</td>

  </tr>

 </tbody>

</table>

bra top




done:      goto done  ; Place holder for last line of executed code

.end                 ; End of program code in this file

You must download your program to your PIC24 hardware and demonstrate the execution of your program on hardware to the TA.

<strong>TA check</strong>: <strong>Show the TA the task 4 results including the final state of the program, data memory, and the watch window. Use a screen capture tool to capture these windows and include them in your lab report. Include your source language program in your lab report.</strong>

<h1>6.     Laboratory Report</h1>

No later than a week from the day the lab is performed, provide the TA a printed copy of the lab report following the ECE383 Lab report Template given on the class website. Each lab group will submit one joint lab report to the TA.  Your report should have the reporting requirements needed for Tasks 1, 2, 3, and 4. <strong>The TA will take off a significant number of points (15 points from total lab grade) if your C and assembly language source does not have the required comments.</strong> The C programs should be appropriately commented. For the assembly programs, the comments should indicate which assembly language source lines implement which C statements