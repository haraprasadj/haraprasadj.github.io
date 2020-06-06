---
layout: post
title: Banker's Rounding - VBScript Round Function Does Not Always Round Up
categories: [TechNotes]
---

I was using VBScript's Round function to validate data on an excel sheet. It was giving
incorrect results, saying many perfect rows were incorrect. Tried all possible fixes and
finally realized it is unfixable.

_Reason:_ VBScript does not always round up.VBScript uses algorithm called Banker's Rounding.

See the links below for details:  
[Reference 1](http://c2.com/cgi/wiki?BankersRounding)  
[Reference 2](http://www.xbeat.net/vbspeed/i_BankersRounding.htm)

Effectively VBScript rounds 1.765 to 1.76 and 1.775 to 1.78 (leaving the last digit even).

So, if we need a function to round every value up, we would need a custom function. The custom
function below is the one I wrote to solve this problem:

    Public Function CRound(Num, Digits):
        TenPower = Int(exp(Digits * log(10)))
        NewNum = Num * TenPower
        RoundedNewNum = sgn(NewNum) * Int(Abs(NewNum) + 0.5)
        CRound = RoundedNewNum / TenPower
    End Function
