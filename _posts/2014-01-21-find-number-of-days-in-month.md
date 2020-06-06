---
layout: post
title: Find Number Of Days In A Month In VBScript
categories: [TechNotes]
---

One interesting function I needed was to find the number of days in a particular month.
Turns out this is more complicated than it sounds. I found an elegant solution online:

    Dim numDays
    numDays = Day(DateAdd("d", -1, CDate((desiredMonth + 1) & "/01/" & Year(Date))))

You just go to the first day of next month, then move back to previous day and there you
have it: last day of current month.

There are several variations to the same logic that I could find. There is just one problem,
this does not work for December because it is the last month. I finally ended up
with this logic:

    nMonth = Inputbox("Enter month number: ")
    If IsDate("31-" & CStr(nMonth) & "-" & CStr(Year(Date))) Then nDays = 31
    ElseIf IsDate("30-" & CStr(nMonth) & "-" & CStr(Year(Date))) Then nDays = 30
    ElseIf IsDate("29-" & CStr(nMonth) & "-" & CStr(Year(Date))) Then nDays = 29
    ElseIf IsDate("28-" & CStr(nMonth) & "-" & CStr(Year(Date))) Then nDays = 28
    End If
    msgbox "Month number " & CStr(nMonth) & " has " & CStr(nDays) & "days"

We can make even the year a variable if needed. Hope this helps someone :)
