---

layout : main
title: Crates of Saw

---

# Hi there, I'm Saw!
I'm a senior Electrical Engineering student from 
Penn State University.  

I enjoy tinkering with electrical components as well as working with Mathematics and Algorithms. I do a lot of side projects in my free time. Please check it out!


* Projects
	* [Real-time Image Filtering using FPGA](#imagefilter)
	* [Capacitive CPAP Mask Programming](#cpap)
	* Messenger App


---
## Real-time Image Filtering using FPGA {#imagefilter}
> This is my chosen project for the Advanced Digital Design class. Two 3x3 sliding window filters are implemented using the Nexys4-DDR board. 

<div class = "ExtraBlurp"> 

<p>Because the path delay of the DSP-components easily exceeds the timing contraints, I came up with a FSM controller to pipeline the 2D-convolution process.</p>

<p>The base images (girl and parrot) are loaded into seperate ram blocks. A 12-bit bus width is used for the ram due to the 12-bits VGA RGB ports of the Nexys4 board. A depth of 30000 is used to store a 200x150 px image.</p>

<p>Several filters such as edge-filter, sobel, gaussian blur, emboss are implemented. They can be selected using the switches located at the bottom of the board.

From right to left, the seven segment digit shows which filter the 1st stage is using, which filter the 2nd stage is using, and which image the two filter is applied on. </p>

</div> {::options parse_block_html="true" /}


{::options parse_block_html="false" /}

![Nexys4 DDR Board hooked up with a VGA display](/img/project_img/fpga.jpg)

<div class = "ImageText"> Unfiltered Parrot / Identity Filter </div> {::options parse_block_html="true" /}
{::options parse_block_html="false" /}

![Unfiltered Parrot](/img/project_img/parrot1.jpg)

<div class = "ImageText"> Parrot with Edge filter </div> {::options parse_block_html="true" /}
{::options parse_block_html="false" /}

![Filtered Parrot](/img/project_img/parrot2.jpg)


<div class = "ImageText"> Parrot after Blur and Edge Filter </div> {::options parse_block_html="true" /}
{::options parse_block_html="false" /}

![Filtered Parrot](/img/project_img/parrot3.jpg)

<div class = "ImageText"> With girl image </div> {::options parse_block_html="true" /}
{::options parse_block_html="false" /}

![Unfiltered girl](/img/project_img/Girl1.jpg)

![Unfiltered girl](/img/project_img/Girl2.jpg)

<div class = "ImageText"> <p>With overlay image. Easily implemented by simply using a few AND and OR gates.
See <a href ="https://en.wikipedia.org/wiki/Mask_(computing)#Image_masks">https://en.wikipedia.org/wiki/Mask_(computing)#Image_masks</a></p>
</div> {::options parse_block_html="true" /}
{::options parse_block_html="false" /}

![Unfiltered girl](/img/project_img/Girl3.jpg)

---

## Capacitive CPAP Mask Programming {#cpap}

