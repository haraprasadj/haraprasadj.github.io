---
layout: post
title: Automating A CSV File Using Excel Object Model
categories: [Software Testing, VBScript]
---

We come across csv files in testing all the time. Usually they are treated as text files for 
automation. But they can be automated like Excel files just as Windows opens them using Excel.  

This is very helpful in some situations, and the way to do it is very simple. Use the 
Workbooks.Open method with an additional parameter, that is all!!  
        
        oXl.Workbooks.Open(filename,,,2)  
        
This is the Format parameter of the Open method which specifies the delimiter in case of 
opening a text file and 2 specifies that the delimiter used is comma.

For a complete description see the [MSDN Reference](http://msdn.microsoft.com/en-us/library/microsoft.office.interop.excel.workbooks.open%28v=office.11%29.aspx)