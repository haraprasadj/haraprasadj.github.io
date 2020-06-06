---
layout: post
title: Selenium - Not Able To Identify Any Element In Internet Exporer
categories: [TechNotes]
---

While trying to automate on IE using Selenium, I hit a roadblock straight away when none of
the web elements were being recognized. This drove me crazy to the extent that I decided to stop
wasting time on Selenium for IE.

Finally found the solution thanks to a Selenium expert, and a very simple one at that.
All I needed to add was the following piece of code:

    DesiredCapabilities capabilities = DesiredCapabilities.internetExplorer();
    capabilities.setCapability("initialBrowserUrl", url);
    WebDriver mydriver = new InternetExplorerDriver(capabilities);
