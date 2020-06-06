---
layout: post
title: Automating Internet Explorer With Protected Mode On
categories: [TechNotes]
---

Test automation tools do not work with IE protected mode on. So to successfully automate an
application on IE, the obvious solution is to just disable it or make the tool ignore it.

This is an effective approach but is this the right approach?

Apparently not. Protected mode is there for a reason, and the tools should be tweaked to work
with it and not vice versa. Of course, when nothing else works, these brute force methods are
the only option.

For QTP to record objects on IE with protected mode on, all that is needed is a patch
QTPWEB_00073 whose description is as follows:  
This patch provides official support for testing applications in Internet Explorer
when Internet Explorer is in protected mode. It includes support for working with Internet
Explorer in Protected Mode on all operating systems that QuickTest Professional supports.

For Selenium the usual fix is to include the lines:

    DesiredCapabilities capabilities = DesiredCapabilities.internetExplorer();
    capabilities.setCapability(InternetExplorerDriver.INTRODUCE_FLAKINESS_BY_IGNORING_SECURITY_DOMAINS, true);

However, the following article describes what this capability means and how
and when to use it:  
[http://jimevansmusic.blogspot.in/2012/08/youre-doing-it-wrong-protected-mode-and.html](http://jimevansmusic.blogspot.in/2012/08/youre-doing-it-wrong-protected-mode-and.html)
