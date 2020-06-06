---
layout: post
title: Single Line If Condition In VBScript
categories: [TechNotes]
---

One of the statements most used by a test automation engineer is the 'If' statement. We use
it for pre-conditions, script logic, post-conditions, reporting and everywhere else. One
problem that is associated is it affects readability sometimes a little and sometimes a lot.
One If-Else condition uses up 5 lines of code as below

    If condition1 Then action1
    Else action2
    End If

It makes a lot of sense to write this in one line and save 4 lines. Fortunately we can write
it in one line as:

    If condition1 Then action1 Else action2

Yes, we don't need "End If" in this case

How about If-ElseIf-Else? Simple, rewrite it as

    If condition1 Then action1 Else: If condition2 Then action2 Else action3

Here we are just writing two lines, one for If-Else and one more for another If-Else which
is part of the Else-If and combine them using ":"
