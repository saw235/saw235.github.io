---

layout : main
title: Crates of Saw

---

# Hi there, I'm Saw!
I'm an Electrical Engineering student from 
Penn State University.  

My hobby is playing the piano but I enjoy tinkering with electrical components as well as working with programming, mathematics and algorithms.
I work on some side projects in my free time. Please check them out!


* Projects
	* [Real-time Image Filtering using FPGA](#imagefilter)
	* [Capacitive CPAP Mask Programming](#cpap)
	* Messenger App


---
## Real-time Image Filtering using FPGA {#imagefilter}
> This is my chosen project for the Advanced Digital Design class. Two 3x3 sliding window filters are implemented using the Nexys4-DDR board. 

<figure class="video_container">
  <iframe width="560" height="315" src="https://www.youtube.com/embed/Z--MAIgVxYw" frameborder="0" allowfullscreen></iframe>
</figure> {::options parse_block_html="true" /}
{::options parse_block_html="false" /}

<div class = "ExtraBlurp"> 

<p>Because the path delay of the DSP-components easily exceeds the timing contraints, I came up with a FSM controller to pipeline the 2D-convolution process.</p>

<p>The base images (girl and parrot) are loaded into seperate ram blocks. A 12-bit bus width is used for the ram due to the 12-bits VGA RGB ports of the Nexys4 board. A depth of 30000 is used to store a 200x150 px image.</p>

<p>Several filters such as edge-filter, sobel, gaussian blur, emboss are implemented. They can be selected using the switches located at the bottom of the board.

From right to left, the seven segment digit shows which filter the 1st stage is using, which filter the 2nd stage is using, and which image the two filter is applied on. </p>

</div> {::options parse_block_html="true" /}
{::options parse_block_html="false" /}

![Nexys4 DDR Board hooked up with a VGA display](/img/project_img/fpga-min.jpg)

<div class = "ImageText"> Unfiltered Parrot / Identity Filter </div> {::options parse_block_html="true" /}
{::options parse_block_html="false" /}

![Unfiltered Parrot](/img/project_img/Parrot1-min.jpg)

<div class = "ImageText"> Parrot with Edge filter </div> {::options parse_block_html="true" /}
{::options parse_block_html="false" /}

![Filtered Parrot](/img/project_img/Parrot2-min.jpg)


<div class = "ImageText"> Parrot after Blur and Edge Filter </div> {::options parse_block_html="true" /}
{::options parse_block_html="false" /}

![Filtered Parrot](/img/project_img/Parrot3-min.jpg)

<div class = "ImageText"> With girl image </div> {::options parse_block_html="true" /}
{::options parse_block_html="false" /}

![Unfiltered girl](/img/project_img/Girl1-min.jpg)

![Unfiltered girl](/img/project_img/Girl2-min.jpg)

<div class = "ImageText"> <p>With overlay image. Easily implemented by simply using a few AND and OR gates.</p><p>
See <a href ="https://en.wikipedia.org/wiki/Mask_(computing)#Image_masks">https://en.wikipedia.org/wiki/Mask_(computing)#Image_masks</a></p>
</div> {::options parse_block_html="true" /}
{::options parse_block_html="false" /}

![Unfiltered girl](/img/project_img/Girl3-min.jpg)

---

## Capacitive CPAP Mask Programming {#cpap}

> Programming Capacitive Sensors into a CPAP mask

<div class = "ExtraBlurp"> 

<p></p>

</div> {::options parse_block_html="true" /}
{::options parse_block_html="false" /}

![GUI](/img/project_img/CPAPGUI.PNG)
![Terminal](/img/project_img/Putty.PNG)

---