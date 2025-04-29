# ece253-exercise-9-input-output-in-arm-assembly-solved
**TO GET THIS SOLUTION VISIT:** [ECE253 Exercise 9-Input/Output in ARM assembly Solved](https://www.ankitcodinghub.com/product/ece253-laboratory-exercise-9-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;110002&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;ECE253 Exercise 9-Input\/Output in ARM assembly Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (2 votes)    </div>
    </div>
The purpose of this lab is to:

1. learn how to interact with memory-mapped devices

2. learn how to use polling to detect external events

1 Preparation

Please refer to the Lab 7 handout for resources related to the ARM processor and the cpulator simulator.

2 Part I

Write an assembly-language program that turns on two LEDR lights at a time on the DE1SoC board. First, the lights LEDR9 and LEDR0 should be on, then LEDR8 and LEDR1, then LEDR7 and LEDR2, and so on. When you get to LEDR5 and LEDR4 being on, the direction should be reversed. Only two LEDR lights are ever on at one time. The effect should be a two lights sweeping first towards the centre, then outwards towards the edges, and so on.

Use a delay so that lights move every 0.25 seconds. To implement the delay, use the MPCORE Private Timer described in the lectures (and also in Section 2.4.1 of the Intel documentation on the Quercus website.) When KEY3 is pressed and released, the sweeping motion should stop. Pressing and releasing KEY3 again should restart the motion of the LEDR lights from where they left off. When the restart occurs, the current LEDRs should remain on for a delay of 0.25s before continuing their motion.

To synchronize with the timer device in your main program, use polled I/O by repeatedly reading the F bit in the timer’s status register. Also use polled I/O to deal with the push button KEY3.

1. All necessary code should be contained in one file: part1.s.

2. You should test your code using the CPUlator simulator or using the DE1-SoC board.

3. There is no tester provided for Part 1.

In Part I, you used the timer to create a delay, and used polled I/O to synchronize with the timer. Also, you used polled I/O to check when KEY3 was pressed. In this part of the exercise, you are to create the same application, but relying entirely on interrupts instead of polled I/O. Both the timer and the KEY need to be handled through Interrupts.

You are given template code on Quercus called part2 template.s. There is a LOT of code here. At the top of the file you will see a number of .equ lines. These are similar to #define in C and can be used as a convenience for you in your code if you wish.

You will need to fill in the missing parts including:

• Provide code for all exception handlers. Specifically look for “FILL IN CODE HERE”

• Complete the code for the PRIV TIMER ISR. It has to modify the global variables LEDR DIRECTION and LEDR PATTERN that are declared in the main program below. The first of these variables specifies if the LEDR lights are currently sweeping to the centre or to the outside, and the second variable sets which lights are currently turned on.

• Complete the code for KEY ISR. This is the push button KEY interrupt service routine. It has to stop and resume the timer when KEY3 is pressed.

• Test your code in the cpulator simulator or the DE1-SoC board. No autotester is provided.

An outline of the main ( start) program that you need to use for this lab is shown below.

.text .global _start

_start:

…initialize the IRQ stack pointer …

…initialize the SVC stack pointer …

BL CONFIG_GIC // configure the ARM generic interrupt controller

BL CONFIG_PRIV_TIMER // configure the MPCore private timer

BL CONFIG_KEYS // configure the pushbutton KEYs

…enable ARM processor interrupts …

LDR R6, =0xFF200000 // red LED base address

MAIN:

LDR R4, LEDR_PATTERN // LEDR pattern; modified by timer ISR

STR R4, [R6] // write to red LEDs B MAIN

/* Configure the MPCore private timer to create interrupts every 0.25 second */

CONFIG_PRIV_TIMER:

LDR R0, =0xFFFEC600 // Timer base address

…code not shown

MOV PC, LR // return

/* Configure the KEYS to generate an interrupt */ CONFIG_KEYS:

LDR R0, =0xFF200050 // KEYs base address

…code not shown

MOV PC, LR // return

.global LEDR_DIRECTION LEDR_DIRECTION:

.word 0 // 0 means moving to centre, 1 means moving to outside

.global LEDR_PATTERN LEDR_PATTERN:

.word 0x201 // 1000000001

4 Submission

Part II is optional and can be completed and demo’d for to 1% bonus added to the final course mark.
