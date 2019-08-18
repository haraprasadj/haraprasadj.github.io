---
layout: post
title: Running BPT Automated Tests In Normal mode
categories: [SoftwareTesting]
---

BPT Automated tests run in Fast mode by default, reasonably so. The test execution performance is 
far better in this mode. I wanted to make it run in Normal mode for 1 run for observing the run 
on a slow application. But I could not see an option to do this.  
I googled frantically and when I could not find any way to do this cursed HP mentally for not
thinking about this.  

Then a brainwave hit me. QTP has its own object model and we should be able to play with it using 
a couple of lines of code. I added a couple of lines to make the Run mode Normal and voila,
the run was in normal mode.  

To be specific, I added the following lines in the initialization script we have:  

    Set oQtp = CreateObject("QuickTest.Application")
    Qtp.Options.run.RunMode = "Normal"  

These lines can be added anywhere, meaning in any component, based on requirement to run a 
particular component in Normal mode.