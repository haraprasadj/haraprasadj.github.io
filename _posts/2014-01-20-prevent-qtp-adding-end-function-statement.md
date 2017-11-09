---
layout: post
title: Prevent QTP From Adding Unnecessary 'End Function' Statements
categories: [Software Testing]
---

QTP is sometimes quirky. One that I encountered is that it adds End Funtion statements that
I don't need while I am trying to define the function.  

Let me explain further. I have my own quirk which led me to realize QTP's quirk. When I define 
a function I leave a space between each parameter like:  

    Public Funtion f1(p1, p2, p3)

So as I keep typing the parameter list with spaces in between I see QTP adding End
Function each time I hit space. It took me some time to understand how to make QTP adjust to my 
quirk. And the solution is quite simple really.  

I just need to open and close the braces first before starting addition of parameters. Meaning
I first type  
        
        Public Function f1()
        
and then add all the parameters and this prevents those unwanted End Function statements