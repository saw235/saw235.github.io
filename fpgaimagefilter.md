---

layout : child
title: Crates of Saw
permalink: fpgaimagefilter.html

---

# Image Filtering Project Implementation

Here I have included the diagrams that I thought are important to understand the implementations of the project. There are specific things like datapath of the controller units, and actual top level implementation that are left out, but those can be easily understood by going over the VHDL codes.

## Top Level Explained

The image below shows the Top Level overview of the filter implementation.
The entire process is fairly straightforward. From the left, the diagram shows the Image being serialized from hardcoded rom, shifted into the kernel filter for processing. The output is then loaded into a buffer and starts another filtering process and finally is outputted in VGA format.

A buffer is not needed but is utilized to simplify the process of two stages filtering. For example, the filters can be implemented directly to filter twice as the pixels are accumulated. The complexity involved, however, may be too much and impractical to implement.

As a seperate functionality, an additionaly image stored in rom can also be overlaid on top of the rom images by performing some simple operations. 
The details can be read [here](https://en.wikipedia.org/wiki/Mask_(computing)#Image_masks)

![Top Level Overview](/img/project_img/Pg1_Top Level Overview.jpg){:class="imgfilterdiagrams"}


---
## Image Filtering Implementation Explained

The three images below shows the implementation behind the sliding window image filtering method.

The first image shows the simplified idea of the entire process, whereas the second image shows the implementation of the sliding window in actualty. 

You can see in this image that the 9 pixel data shifted in forms a 3x3 window. When implementing this, I included the FIFO as part of the window component so that the whole thing consist of only two components: the top part and the bottom part.

#### Filtering using a sliding 3x3 kernel
![Filtering Overview](/img/project_img/Pg2_Filtering Overview.jpg){:class="imgfilterdiagrams"}

#### Actual Implementation
![image-title-here](/img/project_img/Pg3_Implementation Overview.jpg){:class="imgfilterdiagrams"}

The third image shows the convolution unit. In practice, this doesn't work 100% of the time and introduces some bugs due to timing constraints caused by the DSP components (much to my dismay). To avoid that, it is necessary to implement pipelining to perform the multiplication and summation by stages. You can look up on how to do pipelining easily in VHDL by googling for it or simply uses a (Finite State Machine) FSM and think of each operation as a state. My implementation uses a FSM.

#### Convolution Unit
![image-title-here](/img/project_img/Pg4_Convolution Unit.jpg){:class="imgfilterdiagrams"}

---

## Filter Controller

The last two images show the FSM of the controller which figures out when to start processing, when convolve the pixels, when to roll over and when to finish.

Again, some of the states are redundant and can be combined but are seperated for clarity and easier implementation and debugging. 

Do remember that each of the state uses up at least one clock cycle (if no loop), however, and thus introduces delays. If your specific application is a hard real time system (ie, you need the image to be filtered within a specific amount of time), then it might not meet the requirement of the system. The same thing can be said for the pipelining process of the convolution unit.

What you can do at this point is to either increase the clock frequency of the board and deal with a more stringent timing requirements, or come out with a quicker algorithm which requires less clock cycle to complete a full filtering process.

![image-title-here](/img/project_img/Pg5_FSM KernelFilter_3x3.jpg){:class="imgfilterdiagrams"}

![image-title-here](/img/project_img/StateTable.PNG){:class="imgfilterdiagrams"}

