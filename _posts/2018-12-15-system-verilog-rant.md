---
layout: post
title: "System Verilog, OVM, UVM rant and thoughts"
author: "Saw"
categories: journal
tags: [System Verilog, rant]
image: cards.jpg
---

If you have ever done any work with OVM/UVM or System Verilog, you will quickly realize that the online resources for them are almost non-existent, compared to the likes of Python, NodeJs and all their associated web frameworks that is all the rage now. The ones that do exists are really old and in most cases does not do a good job of explaining things.

After working in the front-end semiconductor industry for a few months, I quickly realized that even digital design engineers with more than 4 - 5 years of working experience have very limited understanding on how the OVM/UVM libraries work. In many cases, they are just regurgitating the codebase that was laid down before without having a good understanding of what they are doing.

If the codebase was garbage the week before, you would have a few dozens more files with the same nightmare fuel stuff by the end of next week.

This lack of mastery is caused by multiple things.
1. Firstly, the lack of good and comprehensive online resources is making the learning process a lot slower, as mentioned earlier.

2. Secondly, the digital design engineers and verification engineers themselves mostly comes from a mix-match of Computer and Electrical Engineers, most whom have very little Software Engineering background.

3. Thirdly, difficult learning curve of the System Verilog language itself and OVM/UVM libraries makes it doubly hard for engineers to even begin to comprehend what should've been a reusable, maintainable piece of software architecture and the intent of the libraries themselves. It could take an average person familiar with Javascript a few weeks to learn up AngularJs, but in the case of OVM/UVM, it could easily take up more than a year of constantly applying the concepts of OVM/UVM

It has been very frustrating to see so many bad architecture when most of the people you are working with are brilliant engineers.

To address this, I am planning to do a series of writings in attempt to elucidate some of the common issues and questions that I have faced along my journey of learning up the System Verilog language and the OVM/UVM framework.
