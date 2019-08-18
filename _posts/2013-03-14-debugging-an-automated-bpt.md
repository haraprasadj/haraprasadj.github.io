---
layout: post
title: Debugging An Automated Business Process Test
categories: [SoftwareTesting]
---

Ever since I started using BPT, one of the pain points has been to effectively debug my BPT
test.  

Yes, we can pause the run and start debugging by stepping into the code. But once the current 
component is executed and a new component is loaded, we need to pause again and sometimes
it is difficult to get to the line we need.  

Another approach was to write a function with a line to wait, open the function library 
beforehand with the breakpoint at the Wait command and then placing a function call to this 
function in the component we wish to debug. This works better and more reliably.  

But I was surprised to see that there is a direct method supported by Quality Center (I was on 
QC 10). I really wish I had found this much earlier.  
Go to the Test Plan and open the BPT test and navigate to the Test Script tab.  
You will see a blue play icon (highlighted in red):  

![image]({{ "../assets/2013-03-14-debugging-an-automated-bpt_1.png" }}){:class="img-responsive"}
            
Once you click the icon, you would see a popup as below:  

![image]({{ "../assets/2013-03-14-debugging-an-automated-bpt_2.png" }}){:class="img-responsive"}

Here, you can select the run mode at the test level (using the buttons above) or the component 
level (using the dropdown next to each component) and run the test.  

Awesome, isn't it?